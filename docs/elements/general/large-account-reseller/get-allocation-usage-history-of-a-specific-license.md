# Retrieve Allocation Usage History of a Pooled Subscription

Use this API to retrieve allocation usage history of a pooled subscription.

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission |
|-----------|--------|
| `/partner/external/v3/general/partners/t2-reseller/licenses/{licenseId}/usage/batch` | elements.t2.license.read.all |

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve allocation usage history of a pooled subscription.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/partners/t2-reseller/licenses/{licenseId}/usage/batch` | Retrieves allocation usage history of a pooled subscription. |

## Query Parameters

This section outlines the parameters optional required to specify paging information.

| Parameter | Description | Type | Required |
| --- | --- | --- |--- |
| pageIndex | The page number of the data which will be retrieved. The default value is 1. | integer | No |
| pageSize | The number of records to be retrieved one time. The default value is 100. | integer | No |

### Request Body Parameters

This section outlines the request body parameters required to specify the reseller information.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|ResellerIds|Use this if you want to filter resellers by ID. |`list<string>`|No|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Field | Description | Type |
|---|---|---|
| data | The pooled subscription information. | `List<ResellerLicenseUsage>` |
| metadata.pageIndex | The page index of the result. | integer |
| metadata.pageSize | The page size of the result. | integer |
| metadata.totalCount | The total number of the a specific license usage under the current LAR. | integer |

**Pooled Subscription Information**

| Field | Description | Type |
| --- | --- | --- |
| resellerId | The ID of the reseller. | string |
| email | The reseller's email for the Elements account. | string |
| organization | The company/organization name of the reseller. | string |
| assignedDate | The date when user seats were allocated. It must be in the ISO 8601 format. | string |
| allocatedUserSeat | The number of seats assigned to the reseller. | string |
| unitPrice | The unit price for this allocation. | string |
| status | The pooled subscription acceptance status code:<ul><li>**0** - Pending acceptance</li><li>**1** - Accepted</li><li>**2** - Rejected</li><li>**3** - Returned to </li><li>**4** - Expired</li></ul> | integer |
| createdDate | The creation date of the allocation record. It must be in the ISO 8601 format. | string |
| startDate | The effective start date of the allocation. It must be in the ISO 8601 format. Note that this is for the Fly service only.| string |
| expirationDate | The expiration time of the allocation. It must be in the ISO 8601 format. | string |

## Request Sample

To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.

```json
POST https://graph.avepointonlineservices.com/partner/external/v3/general/partners/t2-reseller/licenses/9d32f11c-****-****-****-8fa729bc6103/usage/batch?pageIndex=1&pageSize=50
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
{
    "data": [
        {
            "resellerId": "9d32f11c-aaaa-bbbb-cccc-8fa729bc6103", // The ID of the reseller.
            "email": "admin@subreseller.com", // The reseller's email for the Elements account.
            "organization": "Sub Reseller Demo Org", // The company/organization name of the reseller.
            "assignedDate": "2026-02-01T00:00:00Z", // The date when user seats were allocated. It must be in the ISO 8601 format.
            "allocatedUserSeat": "10", // The number of seats assigned to the reseller
            "unitPrice": "12.50", // The unit price for this allocation.
            "status": 1, // The pooled subscription acceptance status code
            "createdDate": "2026-02-01T00:00:00Z", // The creation date of the allocation record
            "startDate": "2026-02-01T00:00:00Z", // The effective start time of the allocation
            "expirationDate": "2027-02-01T00:00:00Z" // The expiration time of the allocation
        }
    ],
    "metadata": {
        "pageIndex": 1, // The page index of the result
        "pageSize": 100, // The page size of the result
        "totalCount": 1 // The total number of the a specific license usage under the current LAR
    }
}

```