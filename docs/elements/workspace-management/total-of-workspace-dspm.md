# Retrieve Data Security Posture of Tenant

Use this API to retrieve the data security posture statistics of a specific tenant in Elements.  

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../register-app.md).

| API | Permission |
|-----------|-----------|
| `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/dspm/insights` | elements.wm.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve the data security posture statistics of a specific tenant in Elements.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/dspm/insights`|Retrieves the data security posture statistics.|

## URL Parameters

This section outlines the parameters required to specify which tenant's data security posture statistics you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer ID| string | Yes |
| tenantId | The tenant ID of the customer| string | Yes |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| sensitiveItemsSharedWithEveryone | The number of sensitive items that are shared with the Everyone group. | integer |
| sensitiveItemsSharedWithEveryoneExceptExternalUsers | The number of sensitive items that are shared with the Everyone except external users group. | integer |
| sensitiveItemsSharedViaAnyoneLink | The number of sensitive items that are shared via anyone links.  | integer |
| sensitiveItemsSharedViaLinkForSpecificExternalUsers | The number of sensitive items that are shared via links for specific external users. | integer |
| sensitiveItemsSharedViaOrganizationLink | The number of sensitive items that are shared via organization links. | integer |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/customers/966f35cc-****-4070-****-25cd****2a07/tenants/0c7715b3-****-4c4c-****-f363****acec/overview/dspm/insights
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../Use-AvePoint-Graph-API.md/#http-status-code).

```json 
{
    "sensitiveItemsSharedWithEveryone": 1, // The number of sensitive items that are shared with the Everyone group
    "sensitiveItemsSharedWithEveryoneExceptExternalUsers": 2, // The number of sensitive items that are shared with the Everyone except external users group
    "sensitiveItemsSharedViaAnyoneLink": 3, // The number of sensitive items that are shared via anyone links
    "sensitiveItemsSharedViaLinkForSpecificExternalUsers": 4, // The number of sensitive items that are shared via links for specific external users
    "sensitiveItemsSharedViaOrganizationLink": 5 // The number of sensitive items that are shared via organization links
}