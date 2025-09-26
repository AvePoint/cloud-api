# Get customer tenant user seats

Use this API to get customer tenant user seats. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

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
| customerId | The customer id of the customer.    | string | Yes |
| type | The specific tenant type of the customer.<ul><li>**0** - Microsoft365</li><li>**1** - Salesforce</li><li>**2** - Google</li><li>**3** - Dynamics365</li></ul> | integer    | Yes |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| type | The tenant type of the customer.<ul><li>**0** - Microsoft365</li><li>**1** - Salesforce</li><li>**2** - Google</li><li>**3** - Dynamics365</li></ul> | integer |
| availableUserSeat |  The availableUserSeat of the tenant. | integer |
| assignedUserSeat | The assignedUserSeat of the tenant.    | integer |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}/3rd-party-products/type/{type}/overview
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
{
    "type": 0,
    "availableUserSeat": 25,
    "assignedUserSeat": 25
}
```