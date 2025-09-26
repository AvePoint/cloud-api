# Get the customer's protected data information of Cloud Backup for Microsoft 365

Use this API to get the customer's protected data information of Cloud Backup for Microsoft 365. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `partner/external/v3/general/customers/{customerId}/cloud-backup-m365/overview`|elements.cbprotected.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get the customer's protected data information of Cloud Backup for Microsoft 365.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `partner/external/v3/general/customers/{customerId}/cloud-backup-m365/overview` | Get the customer's protected data information of Cloud Backup for Microsoft 365.|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| customerId               | The id of the customer.                 | string |
| customer     | The email of the customer.       | string |
| serviceType       | The name of the service.      | string |
| serviceModule | The module of the module. | string |
| totalScannedObjects | The total scan objects of the module. | long |
| totalProtectedObjects | The total protect count of the module. | long |
| dataSizeStoredInAvePoint | The avepoint storage data size of the module. | string |
| dataSizeStoredInBYOS | The byos storage data size of the module. | string |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}/cloud-backup-m365/overview
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
[
    {
        "customerId": "f1626c49-****-****-****-97dbdc55fc15",
        "customer": "test_****@avepoint.com",
        "serviceType": "Cloud Backup for Microsoft 365",
        "serviceModule": "Exchange Online",
        "totalScannedObjects": 25,
        "totalProtectedObjects": 25,
        "dataSizeStoredInAvePoint": "0 GB",
        "dataSizeStoredInBYOS": "N/A"
    },
    {
        "customerId": "f1626c49-****-****-****-97dbdc55fc15",
        "customer": "test_****@avepoint.com",
        "serviceType": "Cloud Backup for Microsoft 365",
        "serviceModule": "Microsoft 365 Group",
        "totalScannedObjects": 7,
        "totalProtectedObjects": 7,
        "dataSizeStoredInAvePoint": "0 GB",
        "dataSizeStoredInBYOS": "N/A"
    }
]
```