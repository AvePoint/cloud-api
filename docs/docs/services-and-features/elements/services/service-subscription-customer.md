# Retrieve Service Subscriptions

Use this API to retrieve service subscription details for a specific customer that you manage. With this API, you can efficiently manage and audit customer subscriptions, enhancing the capability to oversee and optimize service usage effectively.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements for Partners > App Registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm)  

| API |Permission  |
|-----------|-----------------|
| `/partner/services/{id}` |  partner.license.read.all |  

## Request

This section provides details on the HTTP method and endpoint used to retrieve service subscription for a specific customer.

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/partner/services/{id}` | Get the service subscription details for a specific customer that you manage. |

## Query Parameters

This section outlines the parameters required to specify which customer's subscription information you want to retrieve.  

| Parameter | Description |
| --- | --- |
| Id | The tenant owner ID of the customer. |

## Responses

The API response provides detailed information about the service subscriptions retrieved. Each service subscription in the response includes various attributes that describe its properties and status.

| Response | Description | Type |
| --- | --- | --- |
| customerId | The tenant owner ID of the customer. | String |
| organization | The organization name of the customer. | String |
| customer | The tenant owner email address of the customer. | String |
| tenantId | The tenant ID of the customer. | String |
| service | The service that the customer has subscriptions for. | String |
| subscriptionModel | The subscription model of the customer’s service. | String |
| purchasedUserSeats | The number of purchased user seats of the customer. | String |
| microsoftLicenseAssigned | The number of assigned Microsoft licenses of the customer. | String |
| microsoftLicenseAvailable | The number of available Microsoft licenses of the customer. | String |
| purchasedCapacity | The purchased storage capacity of the customer. | String |
| protectedCapacity | The protected data size for the customer. | String |
| storage | The storage type of the customer. | String |
| retention | The data retention period of the customer. | String |
| consumedStorage | The consumed storage size of the customer. | String |
| expirationDate | The expiration date of the customer’s service. | String |

## Request Sample

Below is a sample request to retrieve service subscription details for a specific customer, identified by their tenant owner ID.

```json
https://graph-us.avepointonlineservices.com/partner/Services/aaaa75-666-aaaa-bbbb-cccc94cb9af5ea3
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).

```json
{
     "@odata.context": "https://graph.avepointonlineservices.com/partner/$metadata#Services/$entity",  // OData metadata URL for the service entity
    "customerId": "caf94a75-2cc6-43aa-b04b-794cb9af5ea3",  // Unique identifier for the customer
    "organization": "AvePointTest_OOP_BothCB365ServiceAndExpress",  // Name of the organization
    "customer": "APtest_AOSP_OOP_BothCB365ServiceAndExpress@commercial.com",  // Customer's email or username
    "tenantId": "c2350b99-c7a2-4605-b7d4-79e8646f66c3",  // Identifier for the customer's tenant
    "products": [  // Array of products associated with the customer
        {
            "service": "Cloud Backup for IaaS + PaaS - Azure Storage",  // Name of the service
            "subscriptionModel": "N/A",  // Type of subscription model
            "purchasedUserSeats": "N/A",  // Number of user seats purchased; not applicable here
            "microsoftLicenseAssigned": "N/A",  // Number of Microsoft licenses assigned
            "microsoftLicenseAvailable": "133",  // Number of available Microsoft licenses
            "purchasedCapacity": "5 GB",  // Amount of purchased capacity for data protection.
            "protectedCapacity": "0 GB", // Protected data size; not applicable here.
            "storage": "AvePoint storage (Microsoft Azure Blob)",  // Storage type and provider
            "retention": "Retain data for 1 month",  // Data retention policy duration
            "consumedStorage": "N/A",  // Amount of storage currently used
            "expirationDate": "2025-04-05",  // Date when the subscription expires
            "change": "N/A"  // Information on changes, not applicable here
        },
        {
            "service": "Cloud Backup for IaaS + PaaS - Virtual Machine",
            "subscriptionModel": "N/A",
            "purchasedUserSeats": "100",
            "microsoftLicenseAssigned": "124",
            "microsoftLicenseAvailable": "133",
            "purchasedCapacity": "N/A",
            "protectedCapacity": "N/A",
            "storage": "AvePoint storage (Microsoft Azure Blob)",
            "retention": "Retain data for 1 months",
            "consumedStorage": "N/A",
            "expirationDate": "2025-04-05",
            "change": "N/A"
        },
        {
            "service": "Cloud Backup for IaaS + PaaS - Amazon EC2",
            "subscriptionModel": "N/A",
            "purchasedUserSeats": "10",
            "microsoftLicenseAssigned": "124",
            "microsoftLicenseAvailable": "133",
            "purchasedCapacity": "N/A",
            "protectedCapacity": "N/A",
            "storage": "AvePoint storage (Microsoft Azure Blob)",
            "retention": "Retain data for 1 years",
            "consumedStorage": "N/A",
            "expirationDate": "2025-03-01",
            "change": "N/A"
        },
        {
            "service": "Cloud Backup for IaaS + PaaS - Azure SQL",
            "subscriptionModel": "N/A",
            "purchasedUserSeats": "N/A",
            "microsoftLicenseAssigned": "N/A",
            "microsoftLicenseAvailable": "133",
            "purchasedCapacity": "500 GB",
            "protectedCapacity": "0 GB",
            "storage": "AvePoint storage (Microsoft Azure Blob)",
            "retention": "Retain data for 1 months",
            "consumedStorage": "N/A",
            "expirationDate": "2025-04-05",
            "change": "N/A"
        }
    ]
}
```
