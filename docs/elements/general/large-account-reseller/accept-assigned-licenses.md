# Accept Assigned Pooled Subscriptions

Use this API to accept the pooled subscriptions assigned to a reseller.

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission |
|-----------|--------|
| `/partner/external/v3/general/partners/t2-reseller/resellers/{resellerId}/licenses/accept` | elements.t2.license.readwrite.all |

## Request

This section outlines the details of the HTTP method and endpoint used to accept the pooled subscriptions assigned to a reseller.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/partners/t2-reseller/resellers/{resellerId}/licenses/accept` | Accepts the pooled subscriptions assigned to a reseller. |

### Request Body Parameters

This section outlines the request body parameters required to specify the license information.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|licenses| The pooled subscription information. |`List<AcceptPoolModel>`|Yes|

**Pooled Subscription Information**

| Field | Description | Type |
| --- | --- | --- |
|licenseId|The ID of the pooled subscription.|string|Yes|
|paymentType|The payment type of the pooled subscription:<ul><li>**0** - Prepaid</li><li>**1** - Pay as you go</li></ul>|integer|Yes|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the operation result displayed in the response body.

| Field | Description | Type |
| --- | --- | --- |
| acceptStatus | The pooled subscription acceptance status code: <ul><li>**9** - The assigned pooled subscriptions were accepted</li><li>**10** - Failed to accept the assigned pooled subscriptions </li><li>**12** - You cannot accept the same pooled subscriptions assigned from different resellers at the same time</li><li>**13** - The pooled subscriptions were already assigned by another LAR and have already been accepted</li></ul> | integer |

## Request Sample

To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.

```json
https://graph.avepointonlineservices.com/partner/external/v3/general/partners/t2-reseller/resellers/9d32f11c-****-****-****-8fa729bc6103/licenses/accept
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "acceptStatus": 9 // The pooled subscription acceptance status code
}


```