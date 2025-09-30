# Retrieve User Protected Status for Customer

Use this API to retrieve the protected status of users in the customer's tenant by Cloud Backup for Microsoft 365.

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/cloud-backup-m365/users/batch`|elements.cbprotected.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve the user protected status.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/customers/{customerId}/tenants/{tenantId}/cloud-backup-m365/users/batch` | Retrieve the user protected status.|

## Query Parameters

This section outlines the parameters that allow users to specify pagination.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The starting number of the page to get the violated objects. The default value is 1. | integer | No |
| pageSize | The number of objects to display on one page. The default value is 50 and the maximum value allowed is 100. | integer | No |
 
## URL Parameters

This section outlines the parameters required to specify which customer tenant you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The ID of the customer.    | string | Yes |
| tenantId | The tenant ID of the customer.        | string | Yes |

## Request Body Parameters

This section outlines the request body required to specify which tenant user's protected status you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| email | The email address of the tenant user to be retrieved | string | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| id                        | The ID of the tenant user.                          | string || email                     | The email address of the tenant user.                       | string |
| displayName               | The display name of the tenant user.                 | string |
| moduleStatus              | The protected module information of the tenant user.| list |

**Protected module information**

| Field | Description | Type |
| --- | --- | --- |
| Module       | The protected module of the tenant user.  <ul><li>**0** - Mailbox</li><li>**2** - OneDrive</li></ul>               | integer |
| IsProtected  | The protected status of the module.   <ul><li>**true** - Protected</li><li>**false** - Not protected</li></ul>                | boolean |

## Request Sample
To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/f162****-b9d4-****-a165-97db****fc15/tenants/0eaab044-****-4a92-****-93c6****711e/cloud-backup-m365/users/batch
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).
```json
{
    "data": [
        {
            "id": "96c5a607-****-****-****-b1a112d7aeae", // The ID of the tenant user
            "email": "user@domain.onmicrosoft.com", // The email address of the tenant user
            "displayName":"UserA", // The display name of the tenant user
            "moduleStatus":
            [
                {
                    "module":0, // The module of the tenant user: 0 represents mailbox
                    "isProtected": false // Whether the user is protected by Cloud Backup for Microsoft 365: false represents not protected
                },
                {
                    "module":2,
                    "isProtected": true
                }
            ]
        }
    ],
    "metadata": {
        "pageIndex": 1, // The current display page
        "pageSize": 50, // The number of objects on the display page
        "totalCount": 2 // The total number of objects matching the query parameters
    }
}
```