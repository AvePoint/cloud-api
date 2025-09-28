# Retrieve customer tenant protected user status

Use this API to get customer tenant protected user status.

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../../elements/register-app.md).

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

This section outlines the parameters required to specify which customer tenant you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The ID of the customer.    | string | Yes |
| tenantId | The tenant ID of the customer.        | string | Yes |

## Request Body

This section outlines the request body required to specify which tenant user you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| email | The email address of the tenant user to be retrieved | string | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| email                     | The email address of the tenant user.                       | string |
| displayName               | The display name of the tenant user.                 | string |
| moduleStatus.Module       | The module of the tenant user.  <ul><li>**0** - Mailbox</li><li>**2** - OneDrive</li></ul>               | integer |
| moduleStatus.IsProtected  | The protected status of the module.   <ul><li>**true** - Protected</li><li>**false** - Not protected</li></ul>                | boolean |

## Request Sample
To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/f162****-b9d4-****-a165-97db****fc15/tenants/0eaab044-****-4a92-****-93c6****711e/cloud-backup-m365/users/batch
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).html#http-status-code).
```json
{
    "data": [
        {
            "email": "user@domain.onmicrosoft.com",
            "displayName":"UserA",
            "moduleStatus":
            [
                {
                    "module":0, // The module of the tenant user: 0 represents mailbox
                    "isProtected": false // Whether the tenant is protected by Cloud Backup for Microsoft 265: false represents not protected
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