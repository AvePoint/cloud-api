# Retrieve Workspace Compliance Statistics of Tenant

Use this API to retrieve the compliance statistics of workspaces for a specific tenant in Elements.  

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../register-app.md).

| API | Permission |
|-----------|-----------|
| `/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/data-protection/compliance-rate` | elements.wm.read.all |  


## Request

This section outlines the HTTP method and endpoint used to retrieve the compliance statistics of workspaces. It provides a concise description of the action performed by the API call.

| Method | Endpoint | Description |
|-----------|-----------|-----------|
|GET|`/partner/external/wm/customers/{customerId}/tenants/{tenantId}/overview/data-protection/compliance-rate`|Retrieves the compliance statistics of workspaces.|

## URL Parameters

This section outlines the parameters required to specify which tenant's workspace compliance statistics you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer ID | string | Yes |
| tenantId | The tenant ID of the customer | string | Yes |


## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| workspacesInCompliance | The number of workspaces that are in compliance. | integer |
| workspacesOutOfCompliance | The number of workspaces that are out of compliance. | integer |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/customers/966f35cc-****-4070-****-25cd****2a07/tenants/0c7715b3-****-4c4c-****-f363****acec/overview/data-protection/compliance-rate
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../Use-AvePoint-Graph-API.md#http-status-code).

```json 
{
    "workspacesInCompliance": 2438, // The number of workspaces that are in compliance
    "workspacesOutOfCompliance": 1037 // The number of workspaces that are out of compliance
}