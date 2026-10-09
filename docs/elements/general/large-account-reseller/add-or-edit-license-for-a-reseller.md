# Add or Edit a Pooled Subscription for a Reseller

Use this API to add a new pooled subscription to a reseller or update an existing pooled subscription for a reseller.

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission |
|-----------|--------|
| `/partner/external/v3/general/partners/t2-reseller/resellers/{resellerId}/licenses` | elements.t2.license.readwrite.all |

## Request

This section outlines the details of the HTTP method and endpoint used to add a new pooled subscription to a reseller or update an existing pooled subscription for a reseller.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/partners/t2-reseller/resellers/{resellerId}/licenses` | Adds a new pooled subscription to a reseller or updates an existing pooled subscription for a reseller. |

### Request Body Parameters

This section outlines the request body parameters required to specify the pooled subscription information.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|licenseId|The ID of the pooled subscription.|string|Yes|
|product|The product code: <ul><li>**2048** - Cloud Backup for Microsoft 365</li><li>**40** - Baseline management</li><li>**42** - Workspace management</li><li>**49** - User and device management</li><li>**65** - Workspace management - Storage optimization</li></ul> |integer|Yes|
|UserSeat|The number of allocated user seats. |integer|Yes|
|ExpirationTime|The expiration time of the assigned pooled subscription. The time must be in the ISO 8601 format.|string|Yes|
|StartDate|The effective start date. The date must be in the ISO 8601 format. Note that this is for the Fly service only.|string|No|
|PaymentType|The payment type of the pooled subscription:<ul><li>**0** - Prepaid</li><li>**1** - Pay as you go</li></ul>|integer|Yes|
|IsSameAsPool|Indicates whether the expiration time should be same as the pooled subscription. |bool|Yes|
|UnitPrice|The price charged per seat. |decimal|No|
|Currency|The price currency code.|string|No|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the operation result displayed in the response body.

| Field | Description | Type |
| --- | --- | --- |
| resellerId | The ID of the reseller.| string |
| product | The product code: <ul><li>**2048** - Cloud Backup for Microsoft 365</li><li>**40** - Baseline management</li><li>**42** - Workspace management</li><li>**49** - User and device management</li><li>**65** - Workspace management - Storage optimization</li></ul> | integer |
| status | The status code: <ul><li>**1** - The request was processed successfully</li><li>**2** - The request failed</li><li>**3** - Failed to find the pooled subscriptions from the current LAR</li><li>**4** - There are not enough user seats for assignment</li><li>**5** - The defined expiration time of the pooled subscription is after your purchased pooled subscription's expiration time </li><li>**7** - The reseller has already had this pooled subscription </li><li>**8** - The assigned pooled subscription has not been accepted by the reseller yet</li><li>**11** - The defined expiration time is earlier than the current time </li> | integer |

## Request Sample

To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.

```json
POST https://graph.avepointonlineservices.com/partner/external/v3/general/partners/t2-reseller/resellers/9d32f11c-****-****-****-8fa729bc6103/licenses
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "resellerId":"9d32f11c-aaaa-bbbb-cccc-8fa729bc6103", // The ID of the reseller
  "product":2048, // The product code
  "status":1 // The status code
}


```