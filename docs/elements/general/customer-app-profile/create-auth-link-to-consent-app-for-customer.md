# Generate Authorization Link to Authorize Service Apps

Use this API to generate an authorization link that customers can use to authorize or re-authorize service apps for a Microsoft 365 tenant.

This API currently supports the following services: baseline management, security and analysis premium services, Azure security management, and Cloud Backup for Microsoft 365. For the full list of services and their apps, see [Services](./services.md).

## Permissions

The following permission is required to call this API.

Before calling the API, register an app in Elements > API app registration so you can authenticate and authorize access to the Elements API. For details, see [App Registration](../../../elements/register-app.md).

| API   | Permission    |
| ----------------- | ------------------------------- |
| `partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/apps/auth-link` | elements.customers.readwrite.all |

## Request

The following table lists the HTTP method and endpoint.

| Method | Endpoint | Description  |
| ------ | --------------------------------- | -------------------------------------------- |
| POST   | `partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/apps/auth-link` | Generates an authorization link that allows customers to authorize or re-authorize service apps. |

## URL Parameters

The following URL parameters are required when you send the POST request.

| Parameter  | Description   | Type   | Required |
| ---------- | ----------------------------- | ------ | -------- |
| customerId | The ID of the customer.  | string | Yes |
| tenantId   | The ID of the Microsoft 365 tenant.| string | Yes |

## Request Body

The request body contains the following fields.

| Field  | Description  | Type   | Required |
| ------------------ | ---------------------- | --- | ----- |
| consentMethod   | The consent method: <ul><li>**0** - Administrator consent</li><li>**1** - User consent</li></ul> | int  | Yes |
| isReAuth | Indicates whether to re-authorize service apps. <ul><li>**true** - Re-authorize service apps</li><li>**false** - Create and authorize service apps</li></ul>| bool | Yes |
| aadEnvironment | An enumeration value that specifies the Azure Active Directory (AAD) environment type associated with the tenant. For a complete list of valid values, refer to [AAD Environment Types](./aad-environment-types.md). | int | Yes |
| platformEnvironmentType | An enumeration value that specifies the platform environment type associated with the tenant. For a complete list of valid values, refer to [Platform Environment Types](./platform-environment-types.md). | int | Yes |
| productNames | The services whose apps you want to authorize or re-authorize. <ul><li>**PartnerTenantSettingManagement** - Baseline management</li><li>**PartnerWorkspaceOnboarding** - Security and analysis premium services</li><li>**PartnerAzureSecurityManagement** - Azure security management</li><li>**Office365Backup** - Cloud Backup for Microsoft 365</li></ul> | `List<string>` | Yes |
| customRecipientEmails | Email addresses that receive success notifications for each app consent. | List<string> | No |

## Response

If the request is successful, the API returns `200 OK` and the response body contains the following fields.

| Field | Description | Type  |
| ----- | --------| --- |
| id | The ID of the authorization link. | string |
| url | The URL of the authorization link. | string |

## Request Sample

Send a POST request to the endpoint with the required parameters.

```json
{
  "consentMethod": 0, // The consent method
  "isReAuth": false, // Indicates whether to re-authorize service apps
  "aadEnvironment": 0, // An enumeration value that specifies the Azure Active Directory (AAD) environment type associated with the tenant
  "platformEnvironmentType": 0, // An enumeration value that specifies the platform environment type associated with the tenant
  "productNames": ["PartnerWorkspaceOnboarding", "PartnerTenantSettingManagement"], // The service apps you want to authorize or re-authorize
  "customRecipientEmails": ["Jack@TenantABC.com"] // The email addresses that receive success notifications for app consent
}
```

## Response Sample

If the request is successful, the API returns `200 OK` and the requested information in the response body.

For details about HTTP status codes, see [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "id": "9e603ac0-****-****-****-08dea5b34e03", // The ID of the authorization link
  "url": "https://partner.avepointonlineservices.com/app/CustomerAppAuthorizationLink?linkId=9e603ac0-****-****-****-08dea5b34e03&tenantId=ab544a09-****-****-****-5efd0e57c714" // The URL of the authorization link
}
```
