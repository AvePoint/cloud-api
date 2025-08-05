# Retrieve Service Subscriptions for All Your Customers

Use this API to retrieve service subscription details for all the customers you manage. With this API, you can efficiently gather comprehensive subscription data.

## Permissions  

The following permissions are required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm)  

| API |Permission  |
|-----------|--------------|
| `/partner/Services`|partner.license.read.all |  

## Request

This section outlines the method used to retrieve the service subscription for all of your customers. The request method, path, and description are provided for clarity.  

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/partner/services` | Get the service subscription details for all your customers. |

## Response

The API response provides detailed information about the customer's service subscriptions retrieved. Each service subscription in the response includes various attributes that describe its properties and status.

| Response | Description | Type |
| --- | --- | --- |
| customerId | The tenant owner ID of the customer. | string |
| organization | The customer's organization name. | string |
| customer | The tenant owner email address of the customer. | string |
| tenantId | The customer's tenant ID. | string |
|Products| A list of products that the customer has subscribed.| list|

**Product subscriptions**  

| Element | Description | Type |
| --- | --- | --- |
| service | The service that the customer has subscriptions for. | string |
| subscriptionModel | The subscription model of the customer’s service. | string |
| purchasedUserSeats | The number of purchased user seats of the customer. | string |
| purchasedUnits | The number of purchased Microsoft 365 tenants of the customer. | string |
| microsoftLicenseAssigned | The number of assigned Microsoft licenses of the customer. | string |
| microsoftLicenseAvailable | The number of available Microsoft licenses of the customer. | string |
| purchasedCapacity | The purchased capacity for the customer. | string |
| protectedCapacity | The protected data size for the customer. | string |
| storage | The storage type of the customer. | string |
| retention | The data retention period of the customer. | string |
| consumedStorage | The consumed storage size of the customer. | string |
| expirationDate | The expiration date of the customer’s service. | string |
| change | The user seats changes in the pooled license compared with the first day of the current month. | string |
| source | The source of the subscription. | string |
| paymentType | The payment type of the subscription. | string |
| subscriptionName | The subscription name. This parameter is intended specifically for the Fly service. | string |  
| package | The package of the subscription. This parameter is intended specifically for the Cloud Backup for Microsoft 365 service. | string |
| contractEndDate | The contract end date of the subscription. | string |

## Request Sample

The following request structure is designed to query subscriptions for all customers.

```json
https://graph.avepointonlineservices.com/partner/Services
```

## Response Sample

Below is a sample response showcasing the structure and content of the data returned by the API:

```json
{
     "@odata.context": "https://graph.avepointonlineservices.com/partner/$metadata#Services",  // OData context URL for the service metadata
    "value": [  // Array of data objects returned by the service
        {
            "customerId": "b521-b521-b521-b521-b521",  // Unique identifier for the customer
            "organization": "APETest_AOS_QA",  // Name of the customer's organization
            "customer": "cense_us_test@163.com",  // Customer's email address or username
            "tenantId": "417d4762-d9db-4f60-b97e-bf32dc4ddb05,6e3bca9a-a5e9-4b31-858e-c718983cfb70,9a802a7f-61de-49c4-a997-c53f80036c64,dd7a65a8-464b-4a1b-bd5d-66c9a93d5bc4,f0392f21-9bc1-4db1-b323-866eb0d60232",  // Comma-separated list of tenant IDs associated with the customer
            "products": [  // Array of products associated with the customer
                {
                    "service": "Cense",  // Name of the service
                    "subscriptionModel": "N/A",  // Subscription model; not applicable here
                    "purchasedUserSeats": "10",  // Number of user seats purchased
                    "purchasedUnits": "N/A",  // Number of Microsoft 365 tenants purchased; not applicable here
                    "microsoftLicenseAssigned": "0",  // Number of Microsoft licenses assigned
                    "microsoftLicenseAvailable": "0",  // Number of available Microsoft licenses
                    "purchasedCapacity": "N/A",  // Purchased capacity for data to be protected; not applicable here
                    "protectedCapacity": "N/A", // Protected data size; not applicable here.
                    "storage": "N/A",  // Storage details; not applicable here
                    "retention": "N/A",  // Data retention policy; not applicable here
                    "consumedStorage": "N/A",  // Consumed storage capacity; not applicable here
                    "expirationDate": "2025-02-01",  // Date when the subscription expires
                    "change": "N/A",  // Information on changes; not applicable here
                     "source": "AvePoint subscription" // The source of the subscription
                    "paymentType": "Prepaid", // The payment type of the subscription
                    "subscriptionName": "N/A", // The subscription name; not applicable here
                    "package": "N/A", // The package of the subscription; not applicable here
                    "contractEndDate": "N/A" // The contract end date; not applicable here
                }
            ]
        },
        {
            "customerId": "b521-b521-b521-b521-b521",
            "organization": "AvePoint",
            "customer": "aptest_records_fr@163.com",
            "tenantId": "16d5a064-bd41-499e-a70e-670f8745010e,31cdb7b5-2307-4874-9be4-9e459cca4770,47ea9460-25ae-4afd-9d13-57dfc719e290,e20c6264-28ec-4233-ab11-92c9489b80b1",
            "products": [
                {
                    "service": "Opus - Discovery and analysis",
                    "subscriptionModel": "N/A",
                    "purchasedUserSeats": "N/A",
                    "purchasedUnits": "N/A", 
                    "microsoftLicenseAssigned": "0",
                    "microsoftLicenseAvailable": "0",
                    "purchasedCapacity": "1024 GB",
                    "storage": "AvePoint storage",
                    "retention": "N/A",
                    "consumedStorage": "N/A",
                    "expirationDate": "2025-02-01",
                    "change": "N/A",
                    "source": "AvePoint subscription",
                    "paymentType": "Prepaid",
                    "subscriptionName": "N/A",
                    "package": "N/A" ,
                    "contractEndDate": "N/A"
                },
                {
                    "service": "Opus - Storage optimization",
                    "subscriptionModel": "Action and store",
                    "purchasedUserSeats": "N/A",
                    "purchasedUnits": "N/A", 
                    "microsoftLicenseAssigned": "0",
                    "microsoftLicenseAvailable": "0",
                    "purchasedCapacity": "3072 GB",
                    "storage": "AvePoint storage",
                    "retention": "N/A",
                    "consumedStorage": "N/A",
                    "expirationDate": "2025-02-01",
                    "change": "N/A",
                    "source": "AvePoint subscription",
                    "paymentType": "Prepaid",
                    "subscriptionName": "N/A",
                    "package": "N/A" ,
                    "contractEndDate": "N/A"
                },
                {
                    "service": "Opus - Information lifecycle",
                    "subscriptionModel": "N/A",
                    "purchasedUserSeats": "40",
                    "purchasedUnits": "N/A",
                    "microsoftLicenseAssigned": "14",
                    "microsoftLicenseAvailable": "0",
                    "purchasedCapacity": "N/A",
                    "storage": "AvePoint storage",
                    "retention": "N/A",
                    "consumedStorage": "N/A",
                    "expirationDate": "2025-02-01",
                    "change": "N/A",
                    "source": "AvePoint subscription",
                    "paymentType": "Prepaid",
                    "subscriptionName": "N/A",
                    "package": "N/A" ,
                    "contractEndDate": "N/A"
                }
            ]
        }
    ]
}