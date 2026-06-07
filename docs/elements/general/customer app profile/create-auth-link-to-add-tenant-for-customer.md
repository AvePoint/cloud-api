# Generate Authorization Link to Add Microsoft 365 Tenant

Use this API to generate an authorization link that is used to add a Microsoft 365 tenant to Elements.

## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).  

| API | Permissin |
| --- | --------- |
| `partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/auth-link` | elements.customers.readwrite.all, partnerapi.customers.readwrite.all |

## Request

This section outlines the details of the HTTP method and endpoint used by this API.

| Method | Endpoint | Description |
| ------ | ----------------- | -------------------------- |
| POST  | `partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/auth-link` | Generates an authorization link that is to add a Microsoft 365 tenant to Elements. |

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a POST request.

| Parameter | Description  | Type | Required |
| ---------- | -------------------------- | ------ | -------- |
| customerId | The ID of the customer. | string | Yes  |
| tenantId   | The ID of the Microsoft 365 tenant. | string | Yes  |

## Request Body

This section outlines the request body.

| Field   |  Description  | Type   | Required |
| ------ | --------------- | -------------- | -------- |
| aadEnvironment  | An enumeration value that specifies the Azure Active Directory (AAD) environment type associated with the tenant. For a complete list of valid values, refer to [AAD Environment Types](./aad-environment-types.md).| int | Yes |
| tenantFriendlyName | The tenant friendly name. | string | Yes |
| tenantDescription        | The tenant description. | string | No |
| tenantSharePointAdminUrl | The SharePoint admin center URL. | string | No |
| customRecipientEmails    | The email address to which success notification emails for app consent will be sent. | `List<string>`  | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Field | Description | Type |
| ----- | ----------------- | ------------------- |
| id  | The ID of the authorization link. | string |
| url | The URL of the authorization link.| string |

## Request Sample

To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.

```json
{
  "aadEnvironment": 0, // An enumeration value that specifies the Azure Active Directory (AAD) environment type associated with the tenant
  "tenantFriendlyName": "Ogranization ABC", // The tenant friendly name
  "tenantDescription": "This tenant is to...", // The tenant description
  "tenantSharePointAdminUrl": "https://organizationabc-admin.sharepoint.com", // The SharePoint admin center URL
  "customRecipientEmails": [
    "Jack@OrganizationABC.com" // The email address to which success notification emails for each app consent will be sent
  ] 
}
```

## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "id": "cdc31680-****-****-****-08dea5b55c99", // The ID of the authorization link
  "url": "https://partner.avepointonlineservices.com/app/CustomerAppAuthorizationLink?linkId=cdc31680-****-****-****-08dea5b55c99&tenantId=ab544a09-****-****-****-5efd0e57c714" // The URL of the authorization link
}
```
