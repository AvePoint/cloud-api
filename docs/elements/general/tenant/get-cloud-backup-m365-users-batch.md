# Get customer tenant protected user status

Use this API to get customer tenant protected user status.

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/cloud-backup-m365/users/batch`|elements.cbprotected.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get customer tenant protected user status.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/cloud-backup-m365/users/batch` | Get customer tenant protected user status.|

## Query Parameters

This section outlines the parameters optional required to specify paging information about the data you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | No |
| pageSize | The number of customers API will retrieved in a time, the default value is 100. | integer | No |
 
## URL Parameters

This section outlines the parameters required to specify which customer you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer id of the customer.    | string | Yes |
| tenantId | The tenant id of the customer.        | string | Yes |

## Request Body

This section outlines the request body required to specify which tenant user you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| email | The email of the tenant user to be retrived | string | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| email                     | The email of the tenant user.                       | string |
| displayName               | The displayName of the tenant user.                 | string |
| moduleStatus.Module       | The module of the tenant user.  <ul><li>**0** - Mailbox</li><li>**2** - OneDrive</li></ul>               | integer |
| moduleStatus.IsProtected  | The protected status of the module.                  | boolean |

## Request Sample
To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/cloud-backup-m365/users/batch
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
{
    "data": [
        {
            "email": "admin@M365****.onmicrosoft.com",
            "displayName":"M365****",
            "moduleStatus":
            [
                {
                    "module":0,
                    "isProtected": false
                },
                {
                    "module":2,
                    "isProtected": true
                }
            ]
        }
    ],
    "metadata": {
        "pageIndex": 1,
        "pageSize": 50,
        "totalCount": 2
    }
}
```