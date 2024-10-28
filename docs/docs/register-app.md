# Register an App for Modern API

To register an app for the AvePoint Graph Modern API, follow these steps:

1. Access AvePoint Online Services  
   - Sign into AvePoint Online Services with your account. For details, refer to [Sign into AvePoint Online Services](https://cdn.avepoint.com/assets/webhelp/avepoint-online-services/index.htm#!Documents/signintoavepointonlineservices.htm).
2. Navigate to **Administration** > **App registrations**.
3. Register a New App with Required Permissions:  
   1. Click **Create** on the **App registrations** page.  
   2. On the **Create app registration** page, enter a name for the app.  
   3. Click **Add service and permission**.  
   4. In the **Add service and permission** pane, select the services and corresponding permissions that you need to grant to this app, and then click **Add**. 
   >[!NOTE]
   > For the services and permissions that you can grant to the app for using Graph API, refer to [Services and Permissions](#services-and-permissions)
4. Use a certificate or client secret as the app credentials. Credentials enable application to identify themselves to the authentication service when receiving tokens at a web addressable location (using an HTTPS schema). For a higher level of assurance, we recommend using a certification. Follow the instructions below to configure credentials:  
     - The certificate serves as credentials that allow your application to authenticate itself, requiring no interaction from a user at runtime. Refer to [Prepare a Certificate for the Custom Azure App](https://cdn.avepoint.com/assets/webhelp/avepoint-online-services/index.htm#!Documents/prepareacertificateforthecustomazureapp.htm) section in AvePoint Online Services user guide to prepare a certificate.  
        >[!NOTE]
        > If your organization is using AvePoint Opus, you can generate and download a certificate in AvePoint Opus Control Panel > Agent Management. For details, refer to [AvePoint Opus User Guide](https://cdn.avepoint.com/assets/webhelp/avepoint-opus/index.htm#!Documents/registeragents.htm).
     - If you choose to use the client secret, you can generate a client secret effective within 1 year, 2 years, or 3 years. Client secret values cannot be entirely shown once they are saved.  
5. Obtain Application (Client) ID  
   - After you have created the app registration, you can click the Copy button to copy the **Application (client) ID** value which will be used to get an access token in the next step.  
6. Get access token: Based on the credentials of your app registration, refer to the following instructions to get an access token:  
   - Use [Client Secret](#client-secret): You need to send a POST request with the client ID, client secret, scope, and grant type.  
   - Use [Certificate](#certificate). You need to generate a JWT signed with your certificate and send a POST request with the client ID, client assertion (the signed JWT), scope, and grant type. See the DotNet example in the linked section.  


## Services and Permissions  

See the table below for the service and permissions that can be used tor accessing API:  

| AvePoint Cloud Service   | Permission |Usage                   |  
|------------|----------|----------|  
| **AvePoint Online Services**          | audit.read.all | Get the audit records of activities in your AvePoint Online Services tenant. |
 | **Cloud Backup for Dynamics 365**  |  dynamics.readwrite.all   | Get job information from Cloud Backup for Dynamics 365.                |
 | **Cloud Backup for IaaS + PaaS**  |  platformbackup.readwrite.all    | Get job information from Cloud Backup for IaaS + PaaS.                 |
 | **Cloud Backup for Microsoft 365** | microsoft365backup.jobInfo.read.all    | Get job information from Cloud Backup for Microsoft 365. |
 || microsoft365backup.subscriptionInfo.read.all|Get the subscription consumption information of Cloud Backup for Microsoft 365. |
 | **AvePoint Opus**    |     records.readwrite.all  | Connect AvePoint Opus to other systems to access and manage the content. For details, see [AvePoint Opus API for Connector](https://cdn.avepoint.com/assets/webhelp/avepoint-opus/index.htm#!Documents/avepointopusapisforconnector.htm) |c
| **EnPower**    |      enpower.data.read.all                   | Retrieve data from EnPower. For details, see [EnPower Web API](https://cdn.avepoint.com/assets/webhelp/avepoint-enpower/index.htm#!Documents/enpowerwebapi.htm) |
 | **Fly**   |       fly.graph.readwrite.all                       | Perform migrations with Fly. For details, see [Fly Public API](https://cdn.avepoint.com/assets/webhelp/fly/index.htm#!Documents/flypublicapi.htm)                                               |
 | **Insights for Microsoft 365** | insights.graph.readwrite.all        | Retrieve data from Insights for Microsoft 365. For details, see [Insights for Microsoft 365 Web API](https://cdn.avepoint.com/assets/webhelp/insights-for-microsoft-365/index.htm#!Documents/insightsformicrosoft365webapi.htm)                             |
 | **Cloud Governance**  |     cloudgovernance.fullcontrol.all             | Manage data in Cloud Governance. For details, see [AvePoint Cloud Governance Modern API](https://avepointcdn.azureedge.net/assets/webhelp/avepoint-cloud-governance-administrator-guide/index.htm#!Documents/avepointcloudgovernancemodernapi.htm)      |


 ## Client Secret

To obtain an access token using a client secret in an app registration, follow these steps to send a POST request:

1. **Set the Access Token URL**  
   Choose the URL based on your organization's AvePoint environment:

   | AOS Environment             | Access Token URL                                                        |
   |-----------------------------|-------------------------------------------------------------------------|
   | Commercial Environment      | `https://identity.avepointonlineservices.com/connect/token`             |
   | U.S. Government Environment | `https://identity-gov.avepointonlineservices.com/connect/token`         |

2. **Set the Header**  
   - `Content-Type: application/x-www-form-urlencoded`

3. **Set the Request Body Parameters**  
   - `client_id` – Copy the Application (Client) ID from the app registration.
   - `client_secret` – Copy the saved Client Secret from the app registration.
   - `scope` – Set the scope, which is the assigned permission.
   - `grant_type` – Set to `client_credentials`.

4. **Response Details**  
   - `access_token` – The token value.
   - `expires_in` – Indicates the token expiration in seconds.

>[!NOTE]
> You can use Postman to test the POST request as described above.

 ## Certificate  

To obtain an access token using a certificate in an app registration, following the instructions below:  

1. Ensure .NET 6 or later is installed.  
2. Create a new project. Use the following command to create a new project and add the required package.  

        dotnet new console -o AosPublicApiTokenSample --framework net6.0 
        cd ./AosPublicApiTokenSample
        dotnet add package System.IdentityModel.Tokens.Jwt --version 6.30.1
3. Modify `Program.cs`. Open the `AosPublicApiTokenSample` folder and find the `Program.cs` file. Replace the file content with the following code:  

    ```json
    using System.IdentityModel.Tokens.Jwt;
    using System.Net.Http.Json;
    using System.Security.Claims;
    using System.Security.Cryptography.X509Certificates;
    using System.Text.Json.Serialization;
    using Microsoft.IdentityModel.Tokens;

    // Set your app registration information and certificate here
    const string CLIENT_ID = "YOUR_CLIENT_ID"; // Application (Client) ID
    const string SCOPES = "YOUR_SCOPE"; // Permission, e.g., "audit.read.all"
    const string CERTIFICATE_PATH = "YOUR_CERTIFICATE_PATH"; // Path to .pfx or .pem file
    const string CERTIFICATE_PASSWORD = "YOUR_CERTIFICATE_PASSWORD";

    const string IDENTITY_SERVICE_URI = "https://identity.avepointonlineservices.com/connect/token";
    const string AUDIENCE = "https://identity.avepointonlineservices.com/connect/token";

    var clientAssertionValue = GenerateClientAssertion();
    var token = await GetToken(clientAssertionValue);

    PrintToken(token);

    static string GenerateClientAssertion()
    {
        var certificate = new X509Certificate2(CERTIFICATE_PATH, CERTIFICATE_PASSWORD);
        var signingCredentials = new X509SigningCredentials(certificate);

        var claims = new List<Claim>()
        {
            new Claim("jti", Guid.NewGuid().ToString()),
            new Claim("sub", CLIENT_ID)
        };

        var jwtSecurityToken = new JwtSecurityToken(
            CLIENT_ID,
            AUDIENCE,
            claims,
            DateTime.Now,
            DateTime.Now.AddHours(1),
            signingCredentials);

        var clientAssertionValue = new JwtSecurityTokenHandler().WriteToken(jwtSecurityToken);
        return clientAssertionValue;
    }

    static async Task<AosTokenResponse?> GetToken(string clientAssertionValue)
    {
        var requestContent = new FormUrlEncodedContent(new Dictionary<string, string>
        {
            {"grant_type", "client_credentials"},
            {"client_assertion_type", "urn:ietf:params:oauth:client-assertion-type:jwt-bearer"},
            {"client_assertion", clientAssertionValue},
            {"scope", SCOPES},
        });

        try
        {
            var client = new HttpClient();
            var response = await client.PostAsync(IDENTITY_SERVICE_URI, requestContent);

            if (response.IsSuccessStatusCode)
            {
                var token = await response.Content.ReadFromJsonAsync<AosTokenResponse>();
                return token;
            }
            else
            {
                throw new Exception($"Status code: {response.StatusCode}, Raw content: {await response.Content.ReadAsStringAsync()}");
            }
        }
        catch (Exception ex)
        {
            Console.WriteLine($"Get token failed: {ex}");
            return null;
        }
    }

    static void PrintToken(AosTokenResponse? token)
    {
        if (token == null)
        {
            return;
        }

        Console.WriteLine("[Access Token]");
        Console.WriteLine(token.AccessToken);
        Console.WriteLine("[Scope]");
        Console.WriteLine(token.Scope);
    }

    class AosTokenResponse
    {
        [JsonPropertyName("access_token")]
        public string? AccessToken { get; set; }

        [JsonPropertyName("expires_in")]
        public int ExpiresIn { get; set; }

        [JsonPropertyName("token_type")]
        public string? TokenType { get; set; }

        [JsonPropertyName("scope")]
        public string? Scope { get; set; }
    }
    ```

    >[!NOTE]
    > Ajust the `IDENTITY_SERVICE_URI` based on your AvePoint environment.  
    >
    > |AOS Environment| Identity Services URL|
    > |---|---|
    > |Commercial Environment| `https://identity.avepointonlineservices.com`|
    > |U.S. Government Environment|`https://identity-gov.avepointonlineservices.com`|

1. Execute the following command to run the project.  
   `dotnet run`
2. Access token output. The console will display:  

    ```json
    [Access Token]
    eyJhbGc...
    [Scope]
    audit.read.all
