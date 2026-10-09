# Retrieve All Pooled Subscriptions of a Reseller

Use this API to retrieve all pooled subscriptions of a reseller under the current LAR.

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission |
|-----------|--------|
| `/partner/external/v3/general/partners/t2-reseller/resellers/{resellerId}/licenses/batch` | elements.t2.license.read.all |

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve all pooled subscriptions of a reseller under the current LAR.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/partners/t2-reseller/resellers/{resellerId}/licenses/batch` | Retrieves all pooled subscriptions of a reseller under the current LAR. |

## Query Parameters

This section outlines the parameters optional required to specify paging information about the service you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- |--- |
| pageIndex | The page number of the data which will be retrieved. The default value is 1. | integer | No |
| pageSize | The number of records to be retrieved one time. The default value is 100. | integer | No |

### Request Body Parameters

|Parameter|Description | Type|Required?|
|---|---|---|---|
|LicenseIds|Use this if you want to filter pooled subscriptions by ID.|`List<string>`|No|
|Status|Use this if you want to filter pooled subscriptions by status: <ul><li>**0** - Pending acceptance</li><li>**1** - Accepted</li><li>**2** - Rejected</li><li>**3** - Returned to pool</li><li>**4** - Expired</li></ul> |integer|No|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Field | Description | Type |
|---|---|---|
| data | The pooled subscription information. | `List<ResellerLicense>` |
| metadata.pageIndex | The page index of the result. | integer |
| metadata.pageSize | The page size of the result. | integer |
| metadata.totalCount | The total number of the pooled subscriptions of the specified reseller under the current LAR. | integer |

**Pooled Subscription Information**

| Field | Description | Type |
| --- | --- | --- |
| licenseId | The ID of the pooled subscription. | string |
| product | The product code: <ul><li>**2048** - Cloud Backup for Microsoft 365</li><li>**40** - Baseline management</li><li>**42** - Workspace management</li><li>**49** - User and device management</li><li>**65** - Workspace management - Storage optimization</li></ul> | integer |
| poolName | The name of the pooled subscription. | string |
| storage | The storage type: <ul><li>BYOS</li><li>AvePoint storage</li></ul> | string |
| subscriptionName | The display name of the pooled subscription. | string |
| source | The source of the pooled subscription: <ul><li>**5** - AvePoint pooled subscription</li><li>**6** - LAR organization subscription</li></ul>| int |
| unitPrice | The price charged per seat. | string |
| paymentType |  The payment type of the pooled subscription: <ul><li>**0** - Prepaid</li><li>**1** - Pay as you go</li></ul> | int |
| totalUserSeat | The total purchased user seats. | string |
| allocatedUserSeat | The user seats allocated to resellers. | string |
| availableUserSeat | The remaining unallocated user seats. | string |
| startDate | The start date of the pooled subscription. It must be in the ISO 8601 format. Note that this parameter is for the Fly service only. | string |
| expirationDate | The expiration time of the pooled subscription. It must be in the ISO 8601 format. | string |
| status | The pooled subscription acceptance status code:<ul><li>**0** - Pending acceptance</li><li>**1** - Accepted</li><li>**2** - Rejected</li><li>**3** - Returned to pool</li><li>**4** - Expired</li></ul> | int |

## Request Sample

To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/external/v3/general/partners/t2-reseller/resellers/9d32f11c-****-****-****-8fa729bc6103/licenses/batch?pageIndex=1&pageSize=50
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "data": [
        {
            "licenseId": "9d32f11c-aaaa-bbbb-cccc-8fa729bc6103", // The ID of the pooled subscription
            "product": 2048, // The product code
            "poolName": "Cloud Backup for Microsoft 365", // The name of the pooled subscription
            "storage": "AvePoint Managed Storage", // The storage type
            "subscriptionName": "Lars Standard Pool", // The display name of the pooled subscription
            "source": 6, // The source of the pooled subscription
            "unitPrice": "12.50", // The price charged per seat
            "paymentType": 0, // The payment type of the pooled subscription
            "totalUserSeat": "100", // The total purchased user seats
            "allocatedUserSeat": "10", // The user seats allocated to resellers
            "availableUserSeat": "90", // The remaining unallocated user seats
            "startDate": "2025-01-01T00:00:00Z", // The start date of the pooled subscription
            "expirationDate": "2026-01-01T00:00:00Z", // The expiration time of the pooled subscription
            "status": 1
        }
    ],
    "metadata": {
        "pageIndex": 1, // The page index of the result
        "pageSize": 50, // The page size of the result
        "totalCount": 1 // The total number of the pooled subscriptions of the specified reseller under the current T2 partner
    }
}


```
