# Get all services of a customer managed by current partner

Use this API to get all services of a customer managed by current partner. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `partner/external/v3/general/customers/{customerId}/services`|elements.license.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get all services of a customer managed by current partner.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `partner/external/v3/general/customers/{customerId}/services` | Get all services of a customer managed by current partner.|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| customerId               | The customer id of the customer.                 | string |
| organization     | The organization of the customer.       | string |
| customer       | The email address of the customer.      | string |
| products.Service | The service name of the service. | string |
| products.SubscriptionModel      | The subscription model of the license.    | string |
| products.PurchasedUserSeats  | The purchased user seat of the service.            | string |
| products.PurchasedUnits   | The purchased unit of the service.        | string    |
| products.MicrosoftLicenseAssigned      | The microsoft license assigned user seat of the service.                   | string |
| products.MicrosoftLicenseAvailable     | The microsoft license available user seat of the service.                 | string |
| products.PurchasedCapacity     | The purchased capacity of the service.                 | string |
| products.ProtectedCapacity     | The protected capacity of the service.                 | string |
| products.Storage     | The storage of the service.                 | string |
| products.Retention     | The retention of the service.                 | string |
| products.ConsumedStorage     | The consumed storage.                 | string |
| products.ExpirationDate     | The expiration date of the service.                 | string |
| products.Change     | The change of the service.                 | string |
| products.Source     | The source of the service.                 | string |
| products.PaymentType     | The payment type of the service.                 | string |
| products.SubscriptionName     | The subscription name of the service.                 | string |
| products.Package     | The package of the service.                 | string |
| products.ContractEndDate     | The contract end date of the service.                 | string |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}/services
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
{
    "customerId": "1c10525c-121b-4bbc-80a4-2e641bc13421",
    "organization": "test_fly_with_pool_46",
    "customer": "test_fly_with_pool_46@163.com",
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
            "expirationDate": "2025/09/30",
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
            "expirationDate": "2025/08/22",
            "change": "N/A",
            "source": "AvePoint subscription",
            "paymentType": "N/A",
            "subscriptionName": "N/A",
            "package": "N/A",
            "contractEndDate": "N/A"
        }
    ]
}
```