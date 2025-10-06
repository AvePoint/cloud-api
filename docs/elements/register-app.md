# Register an App for API Access

Complete the following steps to register an app for the AvePoint Graph API:

1. Sign in to Elements with your account.
2. Go to the **Settings** page and select **API app registration** in the **Additional** area.
3. On the **API app registration** page, click **Create app registration** under the **Public API** tab.
4. In the **Basic information** step, enter a name for the app and select the corresponding permissions that you need to grant to this app.
5. In the **Customer scope** step, select **All customers**, **Specific customers**, or **Customer groups** as the scope.
6. In the **Certificates and secrets** step, configure the credentials. Credentials enable applications to identify themselves to the authentication service when receiving tokens at a web addressable location (using an HTTPS scheme). For a higher level of assurance, we recommend using a certificate (instead of a client secret) as a credential. Follow the instructions below to configure credentials:
	- Select the **Certificate** tab, and then click **Upload certificate** to upload a certificate (`.cer` file). The certificate serves as credentials that allow your application to authenticate itself, requiring no interaction from a user at runtime. You can refer to [Prepare a Certificate](#prepare-a-certificate) to prepare a certificate.
	- Select the **Client secret** tab, click **Add client secret**, set the effective duration to 1 year, 2 years, or 3 years, and then click **Add** to generate a client secret. Client secret values cannot be entirely shown once they are saved. To get a client secret value for later use, copy and save it upon creation.
6. Click **Save** to save your configurations.

When you finish the registration, click the app name and you can copy the generated Application (Client) ID on the **App registration details** page.


## Prepare a Certificate

To prepare self-signed certificate files based on your scenario, choose one of the following methods.

**Use a Key Vault in Azure to Prepare Certificates**

Before preparing a certificate with this method, make sure you have a key vault in Azure. If you have an Azure subscription but do not have any key vaults, refer to the instructions below to create a Key Vault in Azure.

Make sure you have an Azure subscription that contains Azure Key Vault. Then follow the instructions below:

1. Create an application. This application is only used for Azure Key Vault.
   > a. In the Microsoft Entra admin center (or Microsoft Azure portal), navigate to **Identity > Applications > App registrations** (or **Microsoft Entra ID > App registrations**).

   > b. Click **New registration**.

	> c. On the **Register an application** page, configure the application settings.

	> d. Click **Register** to create your application.

	> e. After the application is created, copy the application ID.
2. Add a client secret for the application.
	> a. After creating the application, click **Certificates & secrets** in the left menu.

	> b. In the **Client secrets** field, click **New client secret**.

	> c. In the **Add a client secret** pane, enter a description for the client secret and select a duration.

	> d. Click **Add**. The value of the client secret is automatically generated and displayed.

	> e.  Copy the client secret value. You will need to provide the value when configuring the encryption profile.

	> **Note:**
	> The value will be hidden after you leave or refresh the page.
3. Create a key vault.
	> a. In the Microsoft Azure portal, enter **Key vaults** in the search box on the top, and then select the first result to access the **Key vaults** page.

	> b. Click **Create**. The **Create a key vault** page appears.

	> c. In the **Basics** tab, provide the basic information for the key vault, and then click the **Access configuration** tab.

	> d. In the **Access policies** section, click **Create**.

	> e. The **Create an access policy** pane appears. In the **Permissions** tab, select the following **Key permissions**:
	  - In the **Key Management Operations** field, select **Get**.
	  - In the **Cryptographic Operations** field, select **Decrypt** and **Encrypt**.

	> f. Click **Next** to go to the **Principal** tab.
	  >> i. In the **Principal** pane, complete the following steps:

	  >> ii. Enter the application name or application ID in the search box.

	  >> iii. Select the application and click **Select** at the bottom.

	  >> iv. Click **Next** at the bottom.

	> g. Click **Create** to add the access policy.

	> h. Click the **Networking** tab.

	> i. Select **Enable public access** which allows all networks to connect to this key vault.

	> j. Click the **Tags** tab and you can add tags to categorize your key vault.

	> k. Click **Review + create** to review all of your configurations first, and then click **Create** at the bottom to create the key vault.

	> **Note:** If you need to change some settings before creating the key vault, you can click the < Previous button to change previous settings.*
4. Create a key.
	> a. On the **Key vaults** page, click the newly created key vault.

	> b. Click **Keys** in **Settings**. In the **Keys** pane, click **Generate/Import** and create a key.

	> c. In the **Keys** pane, click the key name, and then click the current version. The key properties are displayed.

	> d. Copy the key identifier. You will need to provide the key identifier when configuring the encryption profile.

Then, refer to the steps below to prepare the certificate:

1. In the Microsoft Azure portal, navigate to **Key vaults**.
2. On the **Key vaults** page, select a key vault and then select **Certificates** in the left menu.
3. In the **Certificates** panel, click **Generate/Import** and complete the required fields. The screenshot below is a sample certificate. (In the Content Type field, select **PKCS #12**)
4. Click **Create** and wait for the **Status** of the certificate to become **Enabled**. You can click **Refresh** to update the status if needed.
5. Click the name of the certificate, and then select the current version of the certificate.
6. Click **Download in CER format** and **Download in PFX/PEM format** to download the certificate files to your local machine.
7. When you have the certificate (`.pfx` file), you must set a password to protect the certificate.
	> a. Open Windows PowerShell and paste the following script. Replace `[Full path to your PFX]` with the full path of the certificate (`.pfx` file) on your local machine. Note that quotes are required when you enter the commands.

	```powershell
	$pfxPath="[Full path to your PFX]"
	Export-PfxCertificate -Password $(Read-Host -AsSecureString -Prompt "Enter a password to protect the certificate") -PFXData $(Get-PfxData -FilePath $pfxPath) -FilePath $pfxPath
	```
	> b. Press **Enter** to execute the script.

	> **Note:** The `.pfx` file contains your private key.


**Use Windows PowerShell to Prepare Certificates**

To create a self-signed certificate using Windows PowerShell, refer to the following steps:

> **Note:** The steps below are based on running Windows PowerShell on a machine with the Windows 10 or Windows 11 operating system.

1. Right-click **Windows PowerShell** on the machine and select **Run as administrator** from the drop-down list.
2. Use the `New-SelfSignedCertificate` cmdlet to generate certificate files. For example:

	```powershell
	$cert = New-SelfSignedCertificate -Subject CN=AvePointCustomApp -CertStoreLocation 'Cert:\CurrentUser\My' -NotAfter (Get-Date).AddMonths(60)
	```
	Press **Enter** on the keyboard.

3. Export the `.crt` (or `.cer`) file by entering the following command:

	```powershell
	Export-Certificate -Cert $cert -FilePath AvePointCustomApp.crt
	```

	**Note the following:**
	- If you want to export a `.cer` file, replace `.crt` with `.cer` in the cmdlet above.
	- The file will be saved to the current working directory of the PowerShell session. To specify a different directory, use the full path, for example:

	  ```powershell
	  Export-Certificate -Cert $cert -FilePath "C:\\Temp\\AvePointCustomApp.crt"
	  ```

4. Export the `.pfx` file with a password by entering the following command:

	```powershell
	Export-PfxCertificate -Password $(Read-Host -AsSecureString -Prompt "Enter a password to protect the certificate") -Cert $cert -FilePath AvePointCustomApp.pfx
	```

	**Note the following:**
	- The `.pfx` file contains your private key.
	- The file will be saved to the current working directory of the PowerShell session. To specify a different directory, use the full path, for example:

	  ```powershell
	  Export-PfxCertificate -Password $(Read-Host -AsSecureString -Prompt "Enter a password to protect the certificate") -Cert $cert -FilePath "C:\\Temp\\AvePointCustomApp.pfx"
	  ```
	Press **Enter** on the keyboard.

---


## Get the Access Token

Based on the credentials of an app registration in Elements, refer to the following sections.


**Client Secret**

If you want to get the access token with a client secret in an app registration, follow the instructions below to send a POST request:

1. Set the access token URL: `https://identity.avepointonlineservices.com/connect/token`.
2. Set the header to `Content-Type: application/x-www-form-urlencoded`.
3. Set the following parameters in the request body:
   - `grant_type` – Set this value to `client_credentials`.
   - `client_id` – Copy the Application (Client) ID value from the app registration details page and paste the value here.
   - `client_secret` – Copy the Client Secret value that has been saved upon the creation of the app registration, and paste the value here.
4. In the response:
   - The `access_token` node represents the token value.
   - The `expires_in` node represents how many seconds until the token expires.
   - The `scope` node lists the assigned permissions of the app registration.

**Certificate**

Once you have the application (client) ID, get the access token via the application (client) ID to authenticate with Elements APIs.

The following information is required to get an access token:

| Element                  | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| Identity Service URL     | https://identity.avepointonlineservices.com                                 |
| Application (Client) ID  | The application (client) ID you have retrieved.                             |
| Certificate              | The corresponding `.pfx` certificate file of the `.cer` certificate you used when registering the app. |

To get the access token using the above information, create a JSON web token using the Client ID and certificate first, and then use the JSON web token to request an access token of the defined scope from Identity Service.

Below is an example for getting the access token:

```csharp
var identityServiceUrl = "{https://identity.avepointonlineservices.com}";
var client = new HttpClient();
var disco = await client.GetDiscoveryDocumentAsync(identityServiceUrl);
if (disco.IsError)
{
	return;
}
var tokenResponse = await client.RequestClientCredentialsTokenAsync(new ClientCredentialsTokenRequest
{
	Address = disco.TokenEndpoint,
	ClientAssertion = new ClientAssertion()
	{
		Type = OidcConstants.ClientAssertionTypes.JwtBearer,
		Value = CreateClientAuthJwt(disco)
	}
});
if (tokenResponse.IsError)
{    
	return;
}
return tokenResponse.Json;

private static string CreateClientAuthJwt(DiscoveryDocumentResponse response)
{
	var clientId = "{Client ID}";
	var certificateThumbprint = "{Certificate Thumbprint}";

	// set exp to 5 minutes
	var tokenHandler = new JwtSecurityTokenHandler { TokenLifetimeInMinutes = 60 };

	var securityToken = tokenHandler.CreateJwtSecurityToken(
		// iss must be the client_id of our application
		issuer: clientId,
		// aud must be the identity provider (token endpoint)
		audience: response.TokenEndpoint,
		// sub must be the client_id of our application
		subject: new ClaimsIdentity(
		  new List<Claim> { new Claim("sub", clientId),
		  new Claim("jti", Guid.NewGuid().ToString())}),
		// sign with the private key (using RS256 for IdentityServer)
		signingCredentials: new SigningCredentials(
		  new X509SecurityKey(new X509Certificate2(LoadCertificate(certificateThumbprint))), "RS256")
	);
	return tokenHandler.WriteToken(securityToken);
}

private static X509Certificate2 LoadCertificate(string certificateThumbprint)
{
	var store = new X509Store(StoreName.My, StoreLocation.LocalMachine);
	store.Open(OpenFlags.ReadOnly);
	var vCloudCertificate = store.Certificates.Find(
			X509FindType.FindByThumbprint,
			certificateThumbprint,
			false)[0];
	return vCloudCertificate;
}
```
>**Note:**
> The token you get will expire in one hour, and you need to get the token again after the expiration.

