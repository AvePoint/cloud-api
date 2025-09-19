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
|product                             |The product name of the service.  <ul><li>**2048** - Cloud Backup for Microsoft 365</li><li>**270** - Cloud Backup for Exchange Online & OneDrive</li><li>**274** - Cloud Backup Express</li><li>**40** - Baseline management</li><li>**42** - Workspace management</li><li>**49** - User and device management</li><li>**65** - Workspace management - Storage optimization</li></ul>                |int    |Yes|
|licenseType                         |The license type of the service.  <ul><li>**0** - Trial</li><li>**1** - Enterprise</li></ul>                |int      |Yes|
|avepointStorageType                 |The storage type of the service.<ul><li>**0** - AvepointStorageAzure</li><li>**1** - AvepointStorageS3</li><li>**2** - AvepointStorageGCP</li></ul>                                                                                     |int         |Yes|
|retentionYear                       |The retention year of the service.                |int         |Yes|
|byos                                |The byos of the service.                          |bool        |Yes|
|userSeat                            |The user seat of the service.                     |int         |Yes|
|expirationTime                      |The expiration time of the service.               |string      |Yes |
|licenseItems.Resource               |The resource of the service.   <ul><li>**Office365Backup** - Microsoft 365 pool</li><li>**Office365PPBackup** - PowerPlatform pool</li><li>**Office365EXODBackup** - Exchange Online & OneDrive pool</li><li>**PartnerTenantSettingManagement** - Baseline management pool</li><li>**PartnerWorkspaceOnboarding** - Workspace management pool</li><li>**PartnerUserManagement** - User and device management pool</li><li>**PartnerStorageOptimization** - Workspace management - Storage optimization pool</li></ul>                      |string      |Yes|
|licenseItems.SubscriptionSourceType |The source of the service. <ul><li>**1** - AvepointPool</li><li>**2** - MarketplacePool</li><li>**6** - LarsAvepointPool</li></ul>               |int         |Yes|
|licenseItems.IsSameAsPool           |The is same as pool of the service.               |bool        |Yes|
|licenseItems.ExpireTime             |The is expire time of the service.                |string      |Yes|
|licenseItems.SaleType               |The sale type of the service. <ul><li>**0** - Capacity Tier</li><li>**1** - Unlimited Users</li><li>**2** - Unlimited Organization</li></ul>         |int         |Yes|
|licenseItems.PackageType            |The package type of the service. <ul><li>**0** - Standard</li><li>**1** - Core</li><li>**2** - Flex</li></ul>                                      |int         |Yes|
|licenseItems.CustomerSize           |The customer size of the service.                 |int         |Yes|
|licenseItems.ContractEndDate        |The contract end date of the service.             |string      |Yes|
|licenseItems.PaymentType            |The payment type of the service. <ul><li>**0** - Prepaid</li><li>**1** - PayAsYouGo</li></ul>                                                     |int         |Yes|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the created status and customer id and product displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| customerId     | The customer id of the added service.     | string |
| product        | The product of the added service.         | int    |
| status | The status of the created customer.<ul><li>**1** - SaveSuccessful</li><li>**2** - SaveFailed</li><li>**3** - PartnerNoLicense</li><li>**4** - UserSeatNotEnough</li><li>**5** - ExceededExpiredTime</li><li>**6** - CheckFailed</li><li>**7** - LicenseExists</li><li>**11** - LessThanCurrentTime</li><li>**12** - HasSameLicense</li><li>**13** - AlreadyAcceptOtherLicense</li><li>**16** - CheckSuccessful</li><li>**17** - PremiumProductReachLimit</li><li>**18** - ExpiredTimeLessThanOneMonth</li><li>**19** - ReduceUserSeatFailed</li><li>**20** - AssignEXODForCB365ActiveFailed</li></ul> | int |

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}/services

Add Cloud Backup for Microsoft 365/Cloud Backup for Exchange Online & OneDrive Trial license request:
{
  "product": 2048,
  "licenseType": 0,
  "byos": false,
  "avepointStorageType": 0,
  "retentionYear": 1,
  "expirationTime": "2025-10-18T00:00:00Z"
}
Add other products Trial license request:
{
  "product": 42,
  "licenseType": 0,
  "expirationTime": "2025-10-18T00:00:00Z"
}
Add Cloud Backup for Microsoft 365/Cloud Backup for Power Platform/Cloud Backup for Exchange Online & OneDrive pool license request:
{
  "product": 2048,
  "licenseType": 1,
  "byos": false,
  "avepointStorageType": 0,
  "storageProfileId": "",
  "retentionYear": 1,
  "licenseItems": [
    {
      "expireTime": "2025-09-26T00:00:00Z",
      "userSeat": 1,
      "resource": "Office365Backup",
      "isSameAsPool": true,
      "subscriptionSourceType": 1,
      "paymentType": 0,
      "saleType": 0,
      "customerSize": 5,
      "packageType": 0
    },
    {
      "expireTime": "2025-09-26T00:00:00Z",
      "userSeat": 1,
      "resource": "Office365PPBackup",
      "isSameAsPool": true,
      "subscriptionSourceType": 6,
      "paymentType": 1,
      "saleType": 2,
    }
  ]
}
Add other products pool license request:
{
    "product": 42,
    "licenseType": 1,
    "licenseItems": [
      {
        "expireTime": "2025-09-30T00:00:00Z",
        "userSeat": 1,
        "resource": "PartnerTenantSettingManagement",
        "isSameAsPool": true,
        "subscriptionSourceType": 1,
        "paymentType": 0
      }
    ]
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