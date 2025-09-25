# Query Baselines

Use this API to query baselines with optional filtering by baseline id and pagination support.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/baselines/batch` | elements.bm.baseline.read.all or elements.bm.baseline.readwrite.all|  

## Request

This section provides details on the HTTP method and endpoint used to query baselines.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/bm/baselines/batch` | Query all baselines with optional filtering and pagination. |

## Query Parameters

You can use the following optional query parameters in the URL to control pagination:

|Parameter|Description | Type|Required?|
|---|---|---|---|
|pageIndex|The index of the page to retrieve (starting from 1). |integer|No|
|pageSize|The number of records to return per page. The default value is 50. Acceptable range is from 1 to 100.|integer|No|

## Request Body Parameters

You can provide a list of baseline id in the request body to filter the results. This field is optional.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|baselineIds|The ID of the baseline. |string[]|No|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the created baseline id displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| baselineId | The **Id** of the baseline. | string |
| baselineName | The **Name** of the baseline. | string |
| createTime | The create time of the baseline (UTC). | string |
| modifyTime | The last modify time of the baseline (UTC). | string |
| status | The **Status** of the baseline.<ul><li>**1** - Retrieving settings</li><li>**2** - Unused</li><li>**3** - Active</li><li>**4** - Settings retrieval failed</li><li>**5** - Retrieved with exception</li><li>**6** - Draft</li></ul> | integer |

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/bm/baselines/batch?pageIndex=1&pageSize=50

{
    "baselineIds": 
    [
      "0f0cb41b-****-****-****-3a1c39554d0c",
      "5aec2275-****-****-****-3a1c307a28fa"
    ]
}
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the created baseline id displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "data": [
        {
            "baselineId": "0f0cb41b-****-****-****-3a1c39554d0c",
            "baselineName": "Baseline1",
            "createTime": "2025-09-04T10:30:00Z",
            "modifyTime": "2025-09-05T10:30:00Z",
            "status": 1
        },
        {
            "baselineId": "5aec2275-****-****-****-3a1c307a28fa",
            "name": "Baseline2",
            "createTime": "2025-09-06T10:30:00Z",
            "modifyTime": "2025-09-07T10:30:00Z",
            "status": 2
        }
    ],
    "metadata": {
        "pageIndex": 1,
        "pageSize": 50,
        "totalCount": 2
    }
}