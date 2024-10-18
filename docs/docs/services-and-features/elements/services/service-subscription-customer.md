# Retrieve Service Subscriptions

Use this API to retrieve service subscription details for a specific customer that you manage. With this API, you can efficiently manage and audit customer subscriptions, enhancing the capability to oversee and optimize service usage effectively.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements for Partners > App Registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm)  

| API |Permission Required |
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
| CustomerId | The tenant owner ID of the customer. | String |
| Organization | The organization name of the customer. | String |
| Customer | The tenant owner email address of the customer. | String |
| TenantId | The tenant ID of the customer. | String |
| Service | The service that the customer has subscriptions for. | String |
| SubscriptionModel | The subscription model of the customer’s service. | String |
| PurchasedUserSeats | The number of purchased user seats of the customer. | String |
| MicrosoftLicenseAssigned | The number of assigned Microsoft licenses of the customer. | String |
| MicrosoftLicenseAvailable | The number of available Microsoft licenses of the customer. | String |
| PurchasedCapacity | The purchased capacity of the customer. | String |
| Storage | The storage type of the customer. | String |
| Retention | The data retention period of the customer. | String |
| ConsumedStorage | The consumed storage size of the customer. | String |
| ExpirationDate | The expiration date of the customer’s service. | String |

## Request Sample

Below is a sample request to retrieve service subscription details for a specific customer, identified by their tenant owner ID.

```json
https://graph-us.avepointonlineservices.com/partner/Services/aaaa75-666-aaaa-bbbb-cccc94cb9af5ea3
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](/docs/use-avepoint-graph-modern-API/##HTTP-Status-Code).

```json
{
     "@odata.context": "https://graph.avepointonlineservices.com/partner/$metadata#Services/$entity",  // OData metadata URL for the service entity
    "customerId": "caf94a75-2cc6-43aa-b04b-794cb9af5ea3",  // Unique identifier for the customer
    "organization": "AvePointTest_OOP_BothCB365ServiceAndExpress",  // Name of the organization
    "customer": "APtest_AOSP_OOP_BothCB365ServiceAndExpress@commercial.com",  // Customer's email or username
    "tenantId": "c2350b99-c7a2-4605-b7d4-79e8646f66c3",  // Identifier for the customer's tenant
    "products": [  // Array of products associated with the customer
        {
            "service": "Cloud Backup Express",  // Name of the service
            "subscriptionModel": "Enterprise",  // Type of subscription model
            "purchasedUserSeats": "N/A",  // Number of user seats purchased; not applicable here
            "microsoftLicenseAssigned": "0",  // Number of Microsoft licenses assigned
            "microsoftLicenseAvailable": "0",  // Number of available Microsoft licenses
            "purchasedCapacity": "1 GB",  // Amount of storage capacity purchased
            "storage": "AvePoint storage (Microsoft Azure Blob)",  // Storage type and provider
            "retention": "Retain data for 1 years",  // Data retention policy duration
            "consumedStorage": "5.01 GB",  // Amount of storage currently used
            "expirationDate": "08/23/2027",  // Date when the subscription expires
            "change": "N/A"  // Information on changes, not applicable here
        },
        {
            "service": "Cloud Backup for Microsoft 365 - Microsoft 365 services",
            "subscriptionModel": "1 GB/User/Year",
            "purchasedUserSeats": "1",
            "microsoftLicenseAssigned": "0",
            "microsoftLicenseAvailable": "0",
            "purchasedCapacity": "1 GB",
            "storage": "AvePoint storage (Microsoft Azure Blob)",
            "retention": "Retain data for 1 years",
            "consumedStorage": "5.01 GB",
            "expirationDate": "08/23/2027",
            "change": "N/A"
        },
        {
            "service": "Cloud Backup Express",
            "subscriptionModel": "Enterprise",
            "purchasedUserSeats": "N/A",
            "microsoftLicenseAssigned": "0",
            "microsoftLicenseAvailable": "0",
            "purchasedCapacity": "1 GB",
            "storage": "AvePoint storage (Microsoft Azure Blob)",
            "retention": "Retain data for 1 years",
            "consumedStorage": "5.01 GB",
            "expirationDate": "08/23/2027",
            "change": "N/A"
        },
        {
            "service": "Cloud Backup for Microsoft 365 - Microsoft 365 services",
            "subscriptionModel": "1 GB/User/Year",
            "purchasedUserSeats": "1",
            "microsoftLicenseAssigned": "0",
            "microsoftLicenseAvailable": "0",
            "purchasedCapacity": "1 GB",
            "storage": "AvePoint storage (Microsoft Azure Blob)",
            "retention": "Retain data for 1 years",
            "consumedStorage": "5.01 GB",
            "expirationDate": "08/23/2027",
            "change": "N/A"
        }
    ]
}
```
