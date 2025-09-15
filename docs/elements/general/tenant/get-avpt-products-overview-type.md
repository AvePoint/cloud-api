# Get customer avepoint user seats

Use this API to get customer avepoint user seats.

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/avpt-products/overview/type/{productType}`|elements.license.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get customer avepoint user seats.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/partner/external/v3/general/customers/{customerId}/avpt-products/overview/type/{productType}` | Get customer avepoint user seats.|
 
## URL Parameters

This section outlines the parameters required to specify which customer you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer id of the customer.    | string | Yes |
| productType | The specific product type.<ul><li>**2048** - Office 365</li></ul> | int    | Yes |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| productType       | The product type.<ul><li>**2048** - Office 365</li></ul>                           | string |
| availableUserSeat | The availableUserSeat of the product.                 | int |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}//avpt-products/overview/type/{productType}
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
 {
        "productType": 2048,
        "availableUserSeat": 25
}
```