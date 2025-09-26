# Get customer tenant assigned user seats

Use this API to get customer tenant assigned user seats. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/3rd-party-products/type/{type}/users`|elements.license.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get customer tenant assigned user seats.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/customers/{customerId}/3rd-party-products/type/{type}/users` | Get customer M365 assigned user seats.|
 
## URL Parameters

This section outlines the parameters required to specify which customer tenant you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer id of the customer.    | string | Yes |
| type | The specific tenant type of the customer.<ul><li>**0** - Microsoft365</li><li>**1** - Salesforce</li><li>**2** - Google</li><li>**3** - Dynamics365</li></ul> | integer    | Yes |

## Request Body

This section outlines the request body required to specify which users you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| licenseAssignedStatus | The specific field of the user seat.<ul><li>**0** - AvailableUserSeat</li><li>**1** - AvailableUserSeat</li></ul> | integer    | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| id                | The id of the tenant.                                | string |
| name              | The id of the tenant.                                | string |
| availableUserSeat | The availableUserSeat of the tenant.                 | integer |
| assignedUserSeat  | The assignedUserSeat of the tenant.                  | integer |

## Request Sample
To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}/3rd-party-products/type/{type}/users
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
[
    {
        "id": "f04d7aee-****-****-****-65215f92e596",
        "name":"v40t",
        "availableUserSeat": 25,
        "assignedUserSeat": 25
    }
]
```