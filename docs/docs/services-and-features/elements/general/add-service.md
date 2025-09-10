# Add a service to a customer

Use this API to add a service to a customer.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/services` | elements.license.readwrite.all     |

## Request

This section provides details on the HTTP method and endpoint used to add a service to a customer.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/general/customers/{customerId}/services` | Add a service to a customer. |

## Request Body Parameters

You can provide a customer basic information in the request body to onboard a customer. This field is required.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|product                             |The product name of the service.                  |string      |Yes|
|licenseType                         |The license type of the service.                  |string      |Yes|
|avepointStorageType                 |The storage type of the service.<ul><li>**0** - AvepointStorageAzure</li><li>**1** - AvepointStorageS3</li><li>**2** - AvepointStorageGCP</li></ul>                                                                                     |int         |Yes|
|retentionYear                       |The retention year of the service.                |int         |Yes|
|byos                                |The byos of the service.                          |bool        |Yes|
|userSeat                            |The user seat of the service.                     |int         |Yes|
|expirationTime                      |The expiration time of the service.               |long        |Yes |
|licenseItems.SubscriptionSourceType |The source of the service. <ul><li>**1** - AvepointPool</li><li>**2** - MarketplacePool</li><li>**6** - LarsAvepointPool</li></ul>               |int         |Yes|
|licenseItems.IsSameAsPool           |The is same as pool of the service.               |bool        |Yes|
|licenseItems.SaleType               |The sale type of the service. <ul><li>**0** - Capacity Tier</li><li>**1** - Unlimited Users</li><li>**2** - Unlimited Organization</li></ul>         |int         |Yes|
|licenseItems.PackageType            |The package type of the service. <ul><li>**0** - Standard</li><li>**1** - Core</li><li>**2** - Flex</li></ul>                                      |int         |Yes|
|licenseItems.CustomerSize           |The customer size of the service.                 |int         |Yes|
|licenseItems.ContractEndDate        |The contract end date of the service.             |long        |Yes|
|licenseItems.PaymentType            |The payment type of the service. <ul><li>**0** - Prepaid</li><li>**1** - PayAsYouGo</li></ul>                                                     |int         |Yes|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the created status and customer id and product displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| customerId     | The customer id of the added service.     | string |
| product        | The product of the added service.         | string |
| status | The status of the created customer.<ul><li>**1** - SaveSuccessful</li><li>**2** - SaveFailed</li><li>**3** - PartnerNoLicense</li><li>**4** - UserSeatNotEnough</li><li>**5** - ExceededExpiredTime</li><li>**6** - CheckFailed</li><li>**7** - LicenseExists</li><li>**11** - LessThanCurrentTime</li><li>**12** - HasSameLicense</li><li>**13** - AlreadyAcceptOtherLicense</li><li>**16** - CheckSuccessful</li><li>**17** - PremiumProductReachLimit</li><li>**18** - ExpiredTimeLessThanOneMonth</li><li>**19** - ReduceUserSeatFailed</li><li>**20** - AssignEXODForCB365ActiveFailed</li></ul> | int |

## Request Sample

To use this API, send a GET request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}/services

{
    "product": "Office365Backup",
     "licenseType": "Trial",
     "avepointStorageType": 1,
     "retentionYear": 1,
     "byos": false
}
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the created customer id and status displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "customerId":"7e4ffcae-xxxx-xxxx-xxxx-c6efa0b250d5",
    "product":"Office365Backup",
    "status":1
}