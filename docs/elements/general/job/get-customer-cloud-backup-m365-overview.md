# Retrieve Cloud Backup for Microsoft 365 Overview

Use this API to retrieve the customer's protected data information of Cloud Backup for Microsoft 365.

 ## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/cloud-backup-m365/overview`|elements.cbprotected.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve the customer's protected data information of Cloud Backup for Microsoft 365.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `/partner/external/v3/general/customers/{customerId}/cloud-backup-m365/overview` | Retrieve the customer's protected data information of Cloud Backup for Microsoft 365.|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| customerId               | The ID of the customer.                 | string |
| customer     | The email address of the customer.       | string |
| serviceType       | The name of the service.      | string |
| serviceModule | The module of the customer’s Cloud Backup for Microsoft 365 service. | string |
| totalScannedObjects | The number of the scanned objects of the module. | integer |
| totalProtectedObjects | The number of the backed-up objects of the module. | integer |
| dataSizeStoredInAvePoint | The size of the backed-up objects stored in the AvePoint storage. | string |
| dataSizeStoredInBYOS | The size of the backed-up objects stored in BYOS. | string |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/caf9****-2cc6-****-b04b-794c****5ea3/cloud-backup-m365/overview
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../../elements/Use-AvePoint-Graph-API.md#http-status-code).
```json
[
    {
        "customerId": "f1626c49-****-****-****-97db****fc15", // The customer ID
        "customer": "userA@domain.com", // The email address of the customer
        "serviceType": "Cloud Backup for Microsoft 365", // The service name
        "serviceModule": "Exchange Online", // The module of Cloud Backup for Microsoft 365
        "totalScannedObjects": 25, // The number of scanned objects of the module
        "totalProtectedObjects": 25, // The number of backed-up objects of the module
        "dataSizeStoredInAvePoint": "0 GB", // The size of the backed-up objects stored in AvePoint storage
        "dataSizeStoredInBYOS": "N/A" // The size of the backed-up objects stored in BYOS: N/A represents not applicable here 
    },
    {
        "customerId": "f1626c49-****-****-****-97db****fc15",
        "customer": "userB@domain.com",
        "serviceType": "Cloud Backup for Microsoft 365",
        "serviceModule": "Microsoft 365 Group",
        "totalScannedObjects": 7,
        "totalProtectedObjects": 7,
        "dataSizeStoredInAvePoint": "0 GB",
        "dataSizeStoredInBYOS": "N/A"
    }
]
```