# Get customer avepoint user seats

Use this API to get customer avepoint user seats.

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/avpt-products/type/{productType}/overview`|elements.license.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get customer avepoint user seats.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/partner/external/v3/general/customers/{customerId}/avpt-products/type/{productType}/overview` | Get customer avepoint user seats.|
 
## URL Parameters

This section outlines the parameters required to specify which customer you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The customer id of the customer.    | string | Yes |
| productType | The specific product type.<ul><li>**1** - DocAve Online</li><li>**4** - Cloud Governance</li><li>**32** - Cloud Backup for Salesforce</li><li>**40** - Baseline Management</li><li>**41** - Risk Management</li><li>**42** - Workspace Management</li><li>**49** - User Management</li><li>**60** - MyHub</li><li>**65** - WorkSpace Management - Storage Optimization</li><li>**257** - TyGraph</li><li>**2048** - Cloud Backup for Microsoft 365</li><li>**4096** - Cloud Management</li><li>**8192** - Cloud Archiving</li><li>**65536** - Opus</li><li>**131072** - Cloud Backup for Dynamics 365</li><li>**4194304** - Insights</li><li>**8388608** - Policies for Microsoft 365</li><li>**16777216** - Fly</li><li>**33554432** - Cloud Backup for Google Workspace</li><li>**67108864** - Cense</li><li>**134217728** - Enpower</li><li>**1073741824** - Cloud Backup for IaaS + PaaS</li></ul> | integer    | Yes |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| productType       | The product type.<ul><li>**1** - DocAve Online</li><li>**4** - Cloud Governance</li><li>**32** - Cloud Backup for Salesforce</li><li>**40** - Baseline Management</li><li>**41** - Risk Management</li><li>**42** - Workspace Management</li><li>**49** - User Management</li><li>**60** - MyHub</li><li>**65** - WorkSpace Management - Storage Optimization</li><li>**257** - TyGraph</li><li>**2048** - Cloud Backup for Microsoft 365</li><li>**4096** - Cloud Management</li><li>**8192** - Cloud Archiving</li><li>**65536** - Opus</li><li>**131072** - Cloud Backup for Dynamics 365</li><li>**4194304** - Insights</li><li>**8388608** - Policies for Microsoft 365</li><li>**16777216** - Fly</li><li>**33554432** - Cloud Backup for Google Workspace</li><li>**67108864** - Cense</li><li>**134217728** - Enpower</li><li>**1073741824** - Cloud Backup for IaaS + PaaS</li></ul>                           | string |
| availableUserSeat | The availableUserSeat of the product.                 | integer |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}/avpt-products/type/{productType}/overview
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