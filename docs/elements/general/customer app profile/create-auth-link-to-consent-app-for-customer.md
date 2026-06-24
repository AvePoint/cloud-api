# Generate Authorization Link to Authorize Service Apps

Use this API to generate an authorization link. Customers can use this link to authorize or re-authorize their service apps for the Microsoft 365 tenant. Currently, only baseline management and other premium services are supported. For a complete list of services, refer to [Services](./services.md).

## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).  

| API   | Permission    |
| ----------------- | ------------------------------- |
| `partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/apps/auth-link` | elements.customers.readwrite.all |

## Request

This section outlines the details of the HTTP method and endpoint used by this API.

| Method | Endpoint | Description  |
| ------ | --------------------------------- | -------------------------------------------- |
| POST   | `partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/apps/auth-link` | Generates an authorization link that allows customers to authorize or re-authorize service apps. |

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a POST request.

| Parameter  | Description   | Type   | Required |
| ---------- | ----------------------------- | ------ | -------- |
| customerId | The ID of the customer.  | string | Yes |
| tenantId   | The ID of the Microsoft 365 tenant.| string | Yes |

## Request Body

This section outlines the request body.

| Field  | Description  | Type   | Required |
| ------------------ | ---------------------- | --- | ----- |
| consentMethod   | The consent method: <ul><li>**0** - Administrator consent</li><li>**1** - User consent</li></ul> | int  | Yes |
| isReAuth | Indicates whether this is to re-authorize service apps. <ul><li>**true** - Reauthorize service apps</li><li>**false** - Create and authorize service apps</li></ul>| bool | Yes |
| aadEnvironment | An enumeration value that specifies the Azure Active Directory (AAD) environment type associated with the tenant. For a complete list of valid values, refer to [AAD Environment Types](./aad-environment-types.md). | int | Yes |
| platformEnvironmentType | An enumeration value that specifies the platform environment type associated with the tenant. For a complete list of valid values, refer to [Platform Environment Types](./platform-environment-types.md). | int | Yes |
| productNames | Services whose apps you want to authorize or re-authorize. <ul><li>**PartnerTenantSettingManagement** - Baseline management</li><li>**PartnerWorkspaceOnboarding** - Other premium services</li></ul> | `List<string>` | Yes |
| customRecipientEmails | The email addresses to which a success notification email for each app consent will be sent.  | List<string>| No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Field | Description | Type  |
| ----- | --------| --- |
| id | The ID of the authorization link. | string |
| url | The URL of the authorization link. | string |

## Request Sample

To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.

```json
{
  "consentMethod": 0, // The consent method
  "isReAuth": false, // Indicates whether this is to re-authorize service apps
  "aadEnvironment": 0, // An enumeration value that specifies the Azure Active Directory (AAD) environment type associated with the tenant
  "platformEnvironmentType": 0, // An enumeration value that specifies the platform environment type associated with the tenant
  "productNames": ["PartnerWorkspaceOnboarding", "PartnerTenantSettingManagement"], // The service apps that you want to authorize or reauthorize
  "customRecipientEmails": ["Jack@TenantABC.com"] // The email address to which success notification emails for app consent will be sent
}
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "id": "9e603ac0-****-****-****-08dea5b34e03", // The ID of the authorization link
  "url": "https://partner.avepointonlineservices.com/app/CustomerAppAuthorizationLink?linkId=9e603ac0-****-****-****-08dea5b34e03&tenantId=ab544a09-****-****-****-5efd0e57c714" // The URL of the authorization link
}
```
