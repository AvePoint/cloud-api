# Retrieve customer tenant user seats

Use this API to retrieve customer tenant's user seats.

 ## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/3rd-party-products/type/{type}/overview`|elements.license.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get customer tenant user seats.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/partner/external/v3/general/customers/{customerId}/3rd-party-products/type/{type}/overview` | Get customer tenant user seats.|
 
## URL Parameters

This section outlines the parameters required to specify which customer tenant you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The ID of the customer.    | string | Yes |
| type | The tenant type of the customer's tenant.<ul><li>**0** - Microsoft 365</li><li>**1** - Salesforce</li><li>**2** - Google</li><li>**3** - Dynamics 365</li></ul> | integer    | Yes |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| type | The tenant type of the customer.<ul><li>**0** - Microsoft 365</li><li>**1** - Salesforce</li><li>**2** - Google</li><li>**3** - Dynamics 365</li></ul> | integer |
| availableUserSeat |  The number of available user seats of the tenant. | integer |
| assignedUserSeat | The number of assigned user seats of the tenant.    | integer |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/f162****-b9d4-****-a165-97db****fc15/3rd-party-products/type/0/overview
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).html#http-status-code).
```json
{
    "type": 0, // The tenant type of the customer: 0 represents Microsoft 365.
    "availableUserSeat": 25, // The number of available user seats of the tenant.
    "assignedUserSeat": 25 // The number of assigned user seats of the tenant.
}
```