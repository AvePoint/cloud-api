# Retrieve All Services of Customers

Use this API to retrieve the services of customers managed by the current partner. 

 ## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/services/batch`|elements.license.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve the services of customers managed by the current partner.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/customers/services/batch` | Retrieve the services of customers managed by the current partner..|
 

## Query Parameters

This section outlines the parameters optional required to specify paging information about the service you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | No |
| pageSize | The number of customers API will retrieved in a time, the default value is 100. | integer | No |

## Request Body Parameters

This section outlines the request body required to specify which customers you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The ID of the customer to be retrieved | string | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| customerId               | The ID of the customer.                 | string |
| organization     | The organization name of the customer.       | string |
| customer       | The email address of the customer.      | string |
| products          | The service subscription information of the customer.               | list |

**Service subscriptions:**
| Field | Description | Type |
| --- | --- | --- |
| service | The service that the customer has subscriptions for. | string |
| subscriptionModel      | The subscription model of the service.    | string |
| purchasedUserSeats  | The number of purchased user seats of the customer.            | string |
| purchasedUnits   | The purchased unit of the service.        | string    |
| microsoftLicenseAssigned      | The number of assigned Microsoft licenses of the customer.                   | string |
| microsoftLicenseAvailable     | The number of available Microsoft licenses of the customer.                 | string |
| purchasedCapacity     | The purchased capacity for the customer.                 | string |
| protectedCapacity     | The protected capacity for the customer.                 | string |
| storage     | The storage of the service.                 | string |
| retention     | The data retention period of the customer.                 | string |
| consumedStorage     | The consumed storage size of the customer.                 | string |
| expirationDate     | The expiration date of the customer’s service.                 | string |
| change     | The user seats changes in the pooled license compared with the first day of the current month.                 | string |
| source     | The source of the subscription.                 | string |
| paymentType     | The payment type of the subscription.               | string |
| subscriptionName     | The subscription name. This parameter is intended specifically for the Fly service.                 | string |
| package     | The package of the subscription. This parameter is intended specifically for the Cloud Backup for Microsoft 365 service.                 | string |
| contractEndDate     | The contract end date of the subscription.                 | string |

## Request Sample
To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/services/batch
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).html#http-status-code).
```json
{
    "data": [
        {
            "customerId": "1c10525c-****-****-****-2e641bc13421",
            "organization": "OrganizationABC",
            "customer": "user@domain.com",
            "products": [
                {
                    "service": "Cloud Backup for IaaS + PaaS - Unit", // The service that the customer has subscriptions for
                    "subscriptionModel": "N/A", // The subscription model of the service; not applicable here
                    "purchasedUserSeats": "N/A", // The number of purchased user seats of the customer; not applicable here
                    "purchasedUnits": "N/A", // The purchased unit of the service; not applicable here
                    "microsoftLicenseAssigned": "0", // The number of assigned Microsoft licenses of the customer
                    "microsoftLicenseAvailable": "0", // The number of available Microsoft licenses of the customer
                    "purchasedCapacity": "0/1 GB", // The purchased capacity for the customer
                    "protectedCapacity": "0 GB", // The protected capacity for the customer
                    "storage": "Bring your own storage", // The storage of the service
                    "retention": "N/A", // The data retention period of the customer; not applicable here
                    "consumedStorage": "N/A", // The consumed storage size of the customer; not applicable here
                    "expirationDate": "2025-09-26T00:00:00Z", // The expiration date of the customer’s service
                    "change": "N/A", // The user seats changes in the pooled license compared with the first day of the current month; not applicable here
                    "source": "AvePoint pooled subscription", // The source of the subscription
                    "paymentType": "Prepaid", // The payment type of the subscription; not applicable here
                    "subscriptionName": "N/A", // The subscription name; not applicable here
                    "package": "N/A", // The package of the subscription; not applicable here
                    "contractEndDate": "N/A" // The contract end date of the subscription; not applicable here
                },
                {
                    "service": "Fly Migration to Google",
                    "subscriptionModel": "N/A",
                    "purchasedUserSeats": "2",
                    "purchasedUnits": "N/A",
                    "microsoftLicenseAssigned": "0",
                    "microsoftLicenseAvailable": "0",
                    "purchasedCapacity": "N/A",
                    "protectedCapacity": "N/A",
                    "storage": "N/A",
                    "retention": "N/A",
                    "consumedStorage": "N/A",
                    "expirationDate": "2025-09-26T00:00:00Z",
                    "change": "N/A",
                    "source": "AvePoint subscription",
                    "paymentType": "N/A",
                    "subscriptionName": "N/A",
                    "package": "N/A",
                    "contractEndDate": "N/A"
                }
            ]
        },
    ],
    "metadata": {
        "pageIndex": 1,
        "pageSize": 50,
        "totalCount": 1
    }
}
```