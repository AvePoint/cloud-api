# Retrieve Baseline Information

Use this API to retrieve the general information of baselines.

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../register-app.md).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/baselines/batch` | elements.bm.baseline.read.all or elements.bm.baseline.readwrite.all|  

## Request

This section provides details on the HTTP method and endpoint used to retrieve the general information of baselines.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/bm/baselines/batch` | Retrieves the general information of baselines. |

## Query Parameters

You can use the following optional query parameters in the URL to control pagination:

|Parameter|Description | Type|Required?|
|---|---|---|---|
|pageIndex|The index of the page to retrieve (starting from 1). |integer|No|
|pageSize|The number of records to return per page. The default value is 50. Acceptable range is from 1 to 100.|integer|No|

## Request Body Parameters

You can provide a list of baseline IDs in the request body to filter the results. This is optional.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|baselineIds|The ID of the baseline. |string[]|No|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the general information of the queried baselines displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| baselineId | The ID of the baseline. | string |
| baselineName | The name of the baseline. | string |
| createdTime | The created time (UTC) of the baseline. | string |
| modifiedTime | The last modified time (UTC) of the baseline. | string |
| status | The status of the baseline.<ul><li>**1** - Retrieving settings</li><li>**2** - Unused</li><li>**3** - Active</li><li>**4** - Settings retrieval failed</li><li>**5** - Retrieved with exception</li><li>**6** - Draft</li></ul> | integer |

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/bm/baselines/batch?pageIndex=1&pageSize=50

{
    "baselineIds": 
    [
      "0f0cb41b-****-****-****-3a1c39554d0c", // The ID of the baseline
      "5aec2275-****-****-****-3a1c307a28fa"
    ]
}
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the general information of the queried baselines in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](../Use-AvePoint-Graph-API.md#http-status-code).

```json
{
    "data": [
        {
            "baselineId": "0f0cb41b-****-****-****-3a1c39554d0c", // The ID of the baseline
            "baselineName": "Baseline1", // The name of the baseline
            "createdTime": "2025-09-04T10:30:00Z", // The created time (UTC) of the baseline
            "modifiedTime": "2025-09-05T10:30:00Z", // The last modified time (UTC) of the baseline
            "status": 1 // The status of the baseline. 1 represents "Retrieving settings"
        },
        {
            "baselineId": "5aec2275-****-****-****-3a1c307a28fa",
            "name": "Baseline2",
            "createdTime": "2025-09-06T10:30:00Z",
            "modifiedTime": "2025-09-07T10:30:00Z",
            "status": 2
        }
    ],
    "metadata": {
        "pageIndex": 1, // The page index of the current request
        "pageSize": 50, // The number of baselines to be retrieved in one request
        "totalCount": 2 // The total number count that matches the request
    }
}