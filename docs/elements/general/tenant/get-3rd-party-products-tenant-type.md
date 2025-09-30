# Retrieve Customer Tenant User Seats

Use this API to retrieve the numbers of assigned and available user seats of the customer's tenant.

 ## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/3rd-party-products/type/{type}/users`|elements.license.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve the user seat details of customer's tenant.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/customers/{customerId}/3rd-party-products/type/{type}/users` | Retrieve the user seat details of customer's tenant|
 
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
| id                | The ID of the tenant.                                | string |
| name              | The name of the tenant.                                | string |
| availableUserSeat | The number of available user seats of the tenant.                 | integer |
| assignedUserSeat  | The number of assigned user seats of the tenant.                  | integer |

## Request Sample
To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/f162****-b9d4-****-a165-97db****fc15/3rd-party-products/type/0/users
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).
```json
[
    {
        "id": "f04d7aee-****-****-****-65215f92e596", // The ID of the tenant
        "name":"TenantABC", // The name of the tenant
        "availableUserSeat": 25, // The number of available user seats of the tenant
        "assignedUserSeat": 25 // The number of assigned user seats of the tenant
    }
]
```