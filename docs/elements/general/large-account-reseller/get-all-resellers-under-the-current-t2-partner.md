# Retrieve All Resellers under the Current LAR

Use this API to retrieve all resellers under the current LAR.

## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission |
|-----------|--------|
| `/partner/external/v3/general/partners/t2-reseller/resellers/batch` | elements.t2.resellers.read.all |

## Request

This section provides details on the HTTP method and endpoint used to retrieve all resellers under the current LAR.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/general/partners/t2-reseller/resellers/batch` | Retrieves all resellers under the current LAR. |

### Query Parameters

This section outlines the optional paging parameters.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The page number. The default value is 1. | integer | No |
| pageSize | The number of records to be retrieved per page. The default value is 100. | integer | No |

### Request Body Parameters

This section outlines the request body parameters required to specify the reseller information.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|ResellerIds|Use this if you want to filter resellers by ID. |`list<string>`|No|

## Response

If the request has been successfully processed, a 200 OK response will be returned with paginated reseller data.

| Field | Description | Type |
|---|---|---|
| data | The reseller information. | `list<PartnerReseller>` |
| metadata.pageIndex | The page index of the result. | integer |
| metadata.pageSize | The page size of the result. | integer |
| metadata.totalCount | The total number of the resellers under the current LAR. | integer |

**Reseller Information**

| Field | Description | Type |
| --- | --- | --- |
| resellerId | The ID of the reseller. | string |
| inviteEmail | The invitation email for the reseller to register for an Elements account. | string |
| organization | The organization/company name of the reseller. | string |
| email | The reseller's email for the Elements account. | string |
| status | The status code of the reseller: <ul><li>**0** - N/A</li><li>**1** - Mapped</li><li>**2** - Unmapped</li><li>**3** - Pending sign up</li></ul> | int |

## Request Sample

Send POST request with optional filter body and pagination query params.

```json
https://graph.avepointonlineservices.com/partner/external/v3/general/partners/t2-reseller/resellers/batch?pageIndex=1&pageSize=50
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "data": [
        {
            "ResellerId": "9d32f11c-aaaa-bbbb-cccc-8fa729bc6103", // The ID of the reseller
            "InviteEmail": "subreseller@demo.com", // The invitation email for the reseller to register for an Elements account
            "Organization": "Sub Reseller Demo Org", // The organization/company name of the reseller
            "Email": "admin@subreseller.com", // The reseller's administrator contact email
            "Status": 1 // The status code of the reseller
        }
    ],
    "metadata": {
        "pageIndex": 1, // The page index of the result
        "pageSize": 50, // The page size of the result
        "totalCount": 1 // The total number of the resellers under the current LAR
    }
}

```