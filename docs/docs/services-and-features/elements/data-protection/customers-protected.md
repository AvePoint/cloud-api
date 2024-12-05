# Retrieve Protected Data within Cloud Backup for Microsoft 365

Use this API to retrieve detailed information about your customer's protected data within Cloud Backup for Microsoft 365. This API is intended specifically for customers who have subscribed to the Cloud Backup for Microsoft 365 service.

## Permissions  

The following permission is required to call the API.
<!Should APIs be plural here? I think it should be  The following permission is required to call the API. If so, this should be a global change in all of the docs where this sentence appears. Thanks!>

You must register an app through Elements for Partners > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).  

| API | Permission   |
|-----------|-------|
| `/partner/customers/{id}/protected` |partner.cbprotected.read.all |  

## Request

This section outlines the details on the HTTP method and endpoint used to retrieve detailed information about your customer's protected data within Cloud Backup for Microsoft 365.

| Method | Endpoint  | Description |
|-----------|-------|-----------|
| GET | `/partner/customers/{id}/protected` | Retrieves detailed information about your customer's protected data within Cloud Backup for Microsoft 365. |

## Query Parameters  

This section outlines the necessary parameters required to specify which customer's protected data within Cloud Backup for Microsoft 365 you want to retrieve.  

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| Id | The tenant owner ID of the customer. | String | Yes |

## Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| customerId | The tenant owner ID of the customer. | String |
| customer | The tenant owner email address of the customer. | String |
| serviceType | The Cloud Backup for Microsoft 365 service that the customer has the subscription for. | String |
| serviceModule | The module of the customer’s Cloud Backup for Microsoft 365 service. | String |
| totalScannedObjects | The number of the scanned objects. | Int |
| totalProtectedObjects | The number of the backed-up objects. | Int |
| dataSizeStoredInAvePoint | The size of the backed-up objects stored in the AvePoint storage. | Int |
| dataSizeStoredInBYOS | The size of the backed-up objects stored in BYOS. | Int |

## Request Sample  

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.

```
https://graph.avepointonlineservices.com/partner/customers/caf94a75-2cc6-43aa-b04b-794c8baf5ea3/protected
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).

```json
{
    "@odata.context": "https://graph.avepointonlineservices.com/partner/$metadata#Collection(Portal.Api.Model.CustomerOverallProtected)",
    "value": [
        {
            "customerId": "caf94a75-2cc6-43aa-b04b-794cb9af5ea3", // The tenant owner ID of the customer
            "customer": "APtest_AOSP_OOP_BothCB365ServiceAndExpress@commercial.com", // The tenant owner email address of the customer
            "serviceType": "Cloud Backup for Microsoft 365", // The Cloud Backup for Microsoft 365 service that the customer has the subscription for
            "serviceModule": "Exchange Online", // The module of the customer’s Cloud Backup for Microsoft 365 service
            "totalScannedObjects": 0, // The number of the scanned objects
            "totalProtectedObjects": 0, // The number of the backed-up objects
            "dataSizeStoredInAvePoint": "0 GB", // The size of the backed-up objects stored in the AvePoint storage
            "dataSizeStoredInBYOS": "N/A" // The size of the backed-up objects stored in BYOS
        },
        {
            "customerId": "caf94a75-2cc6-43aa-b04b-794cb9af5ea3",
            "customer": "APtest_AOSP_OOP_BothCB365ServiceAndExpress@commercial.com",
            "serviceType": "Cloud Backup for Microsoft 365",
            "serviceModule": "Microsoft 365 Group",
            "totalScannedObjects": 0,
            "totalProtectedObjects": 0,
            "dataSizeStoredInAvePoint": "0 GB",
            "dataSizeStoredInBYOS": "N/A"
        }
    ]
}
```
