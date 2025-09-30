# Add a Service

Use this API to add a service for a customer.

## Permission 

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../../elements/register-app.md).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/services` | elements.license.readwrite.all     |

## Request

This section provides details on the HTTP method and endpoint used to add a service for a customer.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/general/customers/{customerId}/services` | Add a service for a customer. |

## Request Body Parameters

You can provide the service detailed information in the request body to add a service for a customer.

#### Add a Cloud Backup for Microsoft 365/Cloud Backup for Exchange Online & OneDrive trial subscription:

|Parameter|Description | Type|Required?|
|---|---|---|---|
|product                             |The name of the service.  <ul><li>**2048** - Cloud Backup for Microsoft 365</li></ul>                |integer    |Yes|
|licenseType                         |The subscription type of the service.  <ul><li>**0** - Trial</li></ul>                |integer      |Yes|
|avepointStorageType                 |The storage type of the service.<ul><li>**0** - AvePoint storage - Microsoft Azure Blob</li><li>**1** - AvePoint Storage - Amazon S3</li></ul>   |integer         |Yes (No)|
|retentionYear                       |The retention year of the service.                |integer         |Yes (No)|
|byos                                |The storage of the service for BYOS.  <ul><li>**true** - The storage is BYOS.</li><li>**false** - The storage is AvePoint storage.</li></ul>                        |boolean        |No (Yes) |
|storageProfileId                    |The storage profile when BYOS is used.                          |boolean        |No (Yes) |

> [!NOTE]  
> Either **avepointStorageType** and **retentionYear** must be provided, or **byos** must be provided; at least one option is required.

#### Add a Cloud Backup Express/Baseline management/Workspace management/User and device management/Workspace management - storage optimization trial subscription:

|Parameter|Description | Type|Required?|
|---|---|---|---|
|product                             |The name of the service.  <ul><li>**274** - Cloud Backup Express</li><li>**40** - Baseline management</li><li>**42** - Workspace management</li><li>**49** - User and device management</li><li>**65** - Workspace management - storage optimization</li></ul>                 |integer    |Yes|
|licenseType                         |The subscription type of the service.  <ul><li>**0** - Trial</li></ul>                |integer      |Yes|

#### Add a Cloud Backup for Microsoft 365/Cloud Backup for Power Platform/Cloud Backup for Exchange Online & OneDrive pooled subscription:

|Parameter|Description | Type|Required?|
|---|---|---|---|
|product                             |The name of the service.  <ul><li>**2048** - Cloud Backup for Microsoft 365</li></ul>                |integer    |Yes|
|licenseType                         |The subscription type of the service.  <ul><li>**1** - Enterprise</li></ul>                |integer      |Yes|
|avepointStorageType                 |The storage type of the service.<ul><li>**0** - AvePoint storage - Microsoft Azure Blob</li><li>**1** - AvePoint storage - Amazon S3</li></ul>     |integer         |Yes (No)|
|retentionYear                       |The retention year of the service.                |integer     |Yes (No)|
|byos                                |Whether the storage of the service is Bring your own storage.       <ul><li>**true** - The storage is BYOS.</li><li>**false** - The storage is AvePoint storage.</li></ul>                |boolean        |No (Yes)|
|storageProfileId                    |The storage profile for BYOS when BYOS is used.                          |boolean        |No (Yes) |
|licenseItems                        |The subscription items of the service.                  |list        |Yes|

> [!NOTE]  
>Either **avepointStorageType** and **retentionYear** must be provided, or **byos** must be provided; at least one option is required.


**Subscription items:**

|Parameter|Description | Type|Required?|
|---|---|---|---|
|resource               |The resource of the service.   <ul><li>**Office365Backup** - Cloud Backup for Microsoft 365 pool</li><li>**Office365PPBackup** - Cloud Backup for Power Platform pool</li><li>**Office365EXODBackup** - Cloud Backup for Exchange Online & OneDrive pool</li></ul>      |string      |Yes|
|subscriptionSourceType |The source of the service. <ul><li>**1** - AvePoint pool</li><li>**2** - Marketplace pool</li><li>**6** - LARS AvePoint pool</li></ul>               |integer         |Yes|
|isSameAsPool           |Whether the expiration time of the service is the same as the pool. <ul><li>**true** - Same as the pool</li><li>**false** - Different from the pool</li></ul>              |bool        |Yes (No)|
|expireTime             |The expiration time of the service.                |string      |No (Yes)|
|saleType               |The type of the service. <ul><li>**0** - Capacity tier</li><li>**1** - Unlimited users</li><li>**2** - Unlimited organization</li></ul>         |integer         |Yes|
|packageType            |The package type of the service. <ul><li>**0** - Standard</li><li>**1** - Core</li><li>**2** - Flex</li></ul>                                      |integer         |Yes|
|customerSize           |The customer's size of the service.                 |integer         |Yes|
|contractEndDate        |The contract end date of the service.             |string      |No |
|paymentType            |The payment type of the service. <ul><li>**0** - Prepaid</li><li>**1** - Pay as you go</li></ul>    |integer         |Yes|

> [!NOTE]  
>If **isSameAsPool** is **false**, **expireTime** must be provided. If **expireTime** is provided, **isSameAsPool** is not required.
>**PackageType** and **customerSize** are only for Cloud Backup for Microsoft 365/Cloud Backup for Exchange Online & OneDrive.

#### Add a Baseline management/Workspace management/User and device management/Workspace management - Storage optimization pooled subscription:

|Parameter|Description | Type|Required?|
|---|---|---|---|
|product                             |The name of the service.  <ul><li>**40** - Baseline management</li><li>**42** - Workspace management</li><li>**49** - User and device management</li><li>**65** - Workspace management - storage optimization</li></ul>                |integer    |Yes|
|licenseType                         |The subscription type of the service.  <ul><li>**1** - Enterprise</li></ul>                |integer      |Yes|
|licenseItems                        |The subscription items of the service.                  |list        |Yes|

**Subscription items:**

|Parameter|Description | Type|Required?|
|---|---|---|---|
|resource               |The resource of the service.   <ul><li>**PartnerTenantSettingManagement** - Baseline management pool</li><li>**PartnerWorkspaceOnboarding** - Workspace management pool</li><li>**PartnerUserManagement** - User and device management pool</li><li>**PartnerStorageOptimization** - Workspace management - storage optimization pool</li></ul>      |string      |Yes|
|subscriptionSourceType |The source of the service. <ul><li>**1** - AvePoint Pool</li><li>**2** - Marketplace Pool</li><li>**6** - LARS AvePoint Pool</li></ul>               |integer         |Yes|
|isSameAsPool           |Whether the expiration time of the service is the same as the pool. <ul><li>**true** - Same as the pool</li><li>**false** - Different from the pool</li></ul>|boolean        |Yes (No)|
|expireTime             |The expiration time of the service.                |string      |No (Yes)|
|contractEndDate        |The contract end date of the service.             |string      |No |
|paymentType            |The payment type of the service. <ul><li>**0** - Prepaid</li><li>**1** - Pay as you go</li></ul>    |integer         |Yes|

> [!NOTE]  
If **isSameAsPool** is **false**, **expireTime** must be provided. If **expireTime** is provided, **isSameAsPool** is not required.

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information in the response body.

| Response | Description | Type |
| --- | --- | --- |
| customerId     | The ID of the customer.     | string |
| product        | The name of the added service.         | integer    |
| status | The status of adding the service.<ul><li>**1** - Successful</li><li>**2** - Failed</li><li>**3** - Partner has no subscription</li><li>**4** - User seat insufficient</li><li>**5** - Exceeded expiration time</li><li>**6** - Check failed</li><li>**7** - Subscription already exists</li><li>**11** - Expiration time earlier than current time</li><li>**12** - Has same subscription</li><li>**16** - Check successful</li><li>**17** - Premium service reached limit</li><li>**18** - Expiration time less than one month</li><li>**19** - Failed to reduce user seats</li><li>**20** - Failed to assign Exchange Online & OneDrive subscription </li></ul> | integer |

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/general/customers/{caf9****-2cc6-****-b04b-794c****5ea3}/services

Add a Cloud Backup for Microsoft 365/Cloud Backup for Exchange Online & OneDrive trial subscription request:
{
  "product": 2048, // The name of the service: 2048 represents Cloud Backup for Microsoft 365
  "licenseType": 0, // The subscription type of the service: 0 represents trial
  "avepointStorageType": 0, // The storage type of the service: 0 represents the AvePoint storage - Microsoft Azure Blob
  "retentionYear": // The retention year of the service; not applicable here
}

Add a Cloud Backup Express/Baseline management/Workspace management/User and device management/Workspace management - storage optimization trial subscription request:
{
  "product": 42,
  "licenseType": 0
}

Add a Cloud Backup for Microsoft 365/Cloud Backup for Power Platform/Cloud Backup for Exchange Online & OneDrive pool subscription request:
{
  "product": 2048,
  "licenseType": 1,
  "byos": true, // The storage type of the service: true represents Bring your own storage
  "storageProfileId": "96c5****-c6cb-****-9792-b1a1****aeae", // The ID of your storage profile
  "licenseItems": [
    {
      "expireTime": "2025-09-26T00:00:00Z", // The expiration time of the service
      "userSeat": 1, // The number of user seats for the service
      "resource": "Office365Backup", // The resource of the service: Office365Backup represents Cloud Backup for Microsoft 365 pool
      "isSameAsPool": true, // Whether the expiration time of the service is the same as the pool: true represents the expiration time are the same
      "subscriptionSourceType": 1, // The source of the service: 1 represents AvePoint Pool
      "paymentType": 0, // The payment type of the service: 0 represents Prepaid
      "saleType": 0, // The type of the service: 0 represents Capacity tier
      "customerSize": 5, // The customer's size of the service
      "packageType": 0 // The package type of the service; 0 represents Standard
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

Add Baseline management/Workspace management/User and device management/Workspace management - storage optimization pooled subscription request:
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

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).

```json
{
    "customerId":"caf9****-2cc6-****-b04b-794c****5ea3", // The ID of the customer
    "product":2048, // The added service: 2048 represents Cloud Backup for Microsoft 365
    "status":1 // The status of adding the service: 1 represents successful
}
```