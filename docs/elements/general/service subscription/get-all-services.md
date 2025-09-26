# Get services of customers managed by current partner

Use this API to get services of customers managed by current partner. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/services/batch`|elements.license.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get services of customers managed by current partner.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/customers/services/batch` | Get services of customers managed by current partner.|
 

## Query Parameters

This section outlines the parameters optional required to specify paging information about the service you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | No |
| pageSize | The number of customers API will retrieved in a time, the default value is 100. | integer | No |

## Request Body

This section outlines the request body required to specify which users you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId | The ID of the customer to be retrived | string | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| customerId               | The customer id of the customer.                 | string |
| organization     | The organization of the customer.       | string |
| customer       | The email address of the customer.      | string |
| products          | The products information of the customer.               | list |

Product subscription:
| Field | Description | Type |
| --- | --- | --- |
| service | The service name of the service. | string |
| subscriptionModel      | The subscription model of the license.    | string |
| purchasedUserSeats  | The purchased user seat of the service.            | string |
| purchasedUnits   | The purchased unit of the service.        | string    |
| microsoftLicenseAssigned      | The microsoft license assigned user seat of the service.                   | string |
| microsoftLicenseAvailable     | The microsoft license available user seat of the service.                 | string |
| purchasedCapacity     | The purchased capacity of the service.                 | string |
| protectedCapacity     | The protected capacity of the service.                 | string |
| storage     | The storage of the service.                 | string |
| retention     | The retention of the service.                 | string |
| consumedStorage     | The consumed storage of the service.                 | string |
| expirationDate     | The expiration date of the service.                 | string |
| change     | The change of the service.                 | string |
| source     | The source of the service.                 | string |
| paymentType     | The payment type of the service.                 | string |
| subscriptionName     | The subscription name of the service.                 | string |
| package     | The package of the service.                 | string |
| contractEndDate     | The contract end date of the service.                 | string |

## Request Sample
To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/services/batch
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
{
    "data": [
        {
            "customerId": "1c10525c-****-****-****-2e641bc13421",
            "organization": "test_****",
            "customer": "test_****@avepoint.com",
            "products": [
                {
                    "service": "Cloud Backup for IaaS + PaaS - Unit",
                    "subscriptionModel": "N/A",
                    "purchasedUserSeats": "N/A",
                    "purchasedUnits": "N/A",
                    "microsoftLicenseAssigned": "0",
                    "microsoftLicenseAvailable": "0",
                    "purchasedCapacity": "0/1 GB",
                    "protectedCapacity": "0 GB",
                    "storage": "Bring your own storage",
                    "retention": "N/A",
                    "consumedStorage": "N/A",
                    "expirationDate": "2025-09-26T00:00:00Z",
                    "change": "N/A",
                    "source": "AvePoint pooled subscription",
                    "paymentType": "Prepaid",
                    "subscriptionName": "N/A",
                    "package": "N/A",
                    "contractEndDate": "N/A"
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