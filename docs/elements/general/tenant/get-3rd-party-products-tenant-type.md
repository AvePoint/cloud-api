# Retrieve Customer Tenant User Seats

Use this API to retrieve the numbers of assigned and available user seats of the customer's tenant.

 ## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/3rd-party-products/type/{type}/tenants/batch`|elements.license.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve the user seat details of customer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/customers/{customerId}/3rd-party-products/type/{type}/tenants/batch` | Retrieve the user seat details of customer's tenant.|
 
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
| type | The tenant type of the customer.<ul><li>**0** - Microsoft 365</li><li>**1** - Salesforce</li><li>**2** - Google</li><li>**3** - Dynamics 365</li></ul> | integer    | Yes |

## Request Body Parameters

This section outlines the request body required to specify the type of user seats you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| licenseAssignedStatus | The type of the user seats.<ul><li>**0** - Available user seats</li><li>**1** - Assigned user seats</li></ul> | integer    | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| type | The tenant type of the customer.<ul><li>**0** - Microsoft 365</li><li>**1** - Salesforce</li><li>**2** - Google</li><li>**3** - Dynamics 365</li></ul> | integer    | Yes |
| tenantId                | The ID of the tenant.                                | string |
| tenantName              | The name of the tenant.                                | string |
| availableUserSeat | The number of available user seats of the tenant.                 | integer |
| assignedUserSeat  | The number of assigned user seats of the tenant.                  | integer |

## Request Sample
To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/f162****-b9d4-****-a165-97db****fc15/3rd-party-products/type/0/tenants/batch
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).
```json
[
    {
        "type": 0, // The type of the tenant; 0 represents the Microsoft 365 tenant
        "tenantId": "f04d7aee-****-****-****-65215f92e596", // The ID of the tenant
        "tenantName":"TenantABC", // The name of the tenant
        "availableUserSeat": 25, // The number of available user seats of the tenant
        "assignedUserSeat": 25 // The number of assigned user seats of the tenant
    }
    "metadata": {
        "pageIndex": 1, // The current display page
        "pageSize": 50, // The number of objects on the display page
        "totalCount": 2 // The total number of objects matching the query parameters
    }
]
```