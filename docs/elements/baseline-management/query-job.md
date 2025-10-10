# Retrieve Job Information from Process Center

Use this API to retrieve job information from the **Process center** page.

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../register-app.md).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/customers/{customerId}/tenants/{tenantId}/process-center/jobs/batch` | elements.bm.tenant.read.all or elements.bm.tenant.readwrite.all |  

## Request

This section provides details on the HTTP method and endpoint used to retrieve job information from the **Process center** page.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/bm/customers/{customerId}/tenants/{tenantId}/process-center/jobs/batch` | Retrieves job information from the **Process center** page. |

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a POST request.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| customerId | The ID of the customer. | string | Yes |
| tenantId | The ID of the tenant. | string | Yes |

## Query Parameters

You can use the following optional query parameters in the URL to control pagination:

|Parameter|Description | Type|Required?|
|---|---|---|---|
|pageIndex|The index of the page to retrieve. The default value is 1. |integer|No|
|pageSize|The number of records to return per page. The default value is 50, and the acceptable range is from 1 to 100.|integer|No|

## Request Body Parameters

You can provide a list of job IDs in the request body to filter the results. This is optional.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|jobIds|The IDs of the jobs. |string[] |No|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the retrieved job information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| jobId | The ID of the job. | string |
| type | The type of the job. <ul><li>**1** - Apply baseline</li><li>**2** - Auto-alignment</li><li>**3** - Create baseline</li><li>**4** - Detect drift</li><li>**5** - Deploy</li><li>**6** - Deploy detected deviations</li><li>**7** - Daily tenant backup</li><li>**8** - Edit tenant configurations </li><li>**9** - Restore to a specific date</li><li>**10** - Restore</li></ul> | integer |
| status | The status of the job.<ul><li>**0** - Waiting</li><li>**1** - In progress</li><li>**2** - Finished</li><li>**3** - Failed</li><li>**4** - Skipped</li><li>**5** - Finished with exception</li></ul> | integer |

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/bm/customers/38c6a73d-****-****-****-75b0f1959474/tenants/a2145aa5-****-****-****-7fffd6e0cc68/process-center/jobs/batch?pageIndex=1&pageSize=50

{
    "jobIds": 
    [
      "a7bd3e1b-****-****-****-243c4df89a2d" // The ID of the job
    ]
}
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the job statuses retrieved from the **Process center** page displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../Use-AvePoint-Graph-API.md#http-status-code).

```json
{
    "data": [
        {
            "jobId": "a7bd3e1b-****-****-****-243c4df89a2d", // The ID of the job
            "type": 1, // The type of the job
            "status": 2  // The status of the job
        }
    ],
    "metadata": {
        "pageIndex": 1, // The page index of the current request
        "pageSize": 5, // The number of jobs to be retrieved in one request
        "totalCount": 1 // The total number count that matches the request
    }
}