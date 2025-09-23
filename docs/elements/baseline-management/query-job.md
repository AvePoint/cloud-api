# Query process center job

Use this API to query process center jobs with optional filtering and pagination support.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/customers/{customerId}}/tenants/{tenantId}/process-center/jobs/batch` | elements.bm.tenant.read.all or elements.bm.tenant.readwrite.all |  

## Request

This section provides details on the HTTP method and endpoint used to query job.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/bm/customers/{customerId}}/tenants/{tenantId}/process-center/jobs/batch` | Query all jobs with optional filtering and pagination. |

## Query Parameters

You can use the following optional query parameters in the URL to control pagination:

|Parameter|Description | Type|Required?|
|---|---|---|---|
|pageIndex|The index of the page to retrieve (starting from 1). |int|No|
|pageSize|The number of records to return per page. The default value is 50. Acceptable range is from 1 to 100.|int|No|

## Request Body Parameters

You can provide a list of baselineIds in the request body to filter the results. This field is optional.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|jobIds|The job ID of the job. |string array|No|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the job info in the response body.

| Response | Description | Type |
| --- | --- | --- |
| jobId | The job id of the job. | string |
| type | The type of the job. <ul><li>**1** - Apply baseline</li><li>**2** - Auto-alignment</li><li>**3** - Create baseline</li><li>**4** - Detect drift</li><li>**5** - Deploy</li><li>**6** - Deploy detected deviations</li><li>**7** - Daily tenant backup</li><li>**8** - Edit tenant configurations </li><li>**9** - Restore to a specific date</li><li>**10** - Restore</li></ul> | int |
| status | The **Status** of the baseline.<ul><li>**0** - Waiting</li><li>**1** - In progress</li><li>**2** - Finished</li><li>**3** - Failed</li><li>**4** - Skipped</li><li>**5** - Finished with exception</li></ul> | int |

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/bm/customers/{customerId}}/tenants/{tenantId}/process-center/jobs/batch?pageIndex=1&pageSize=50

//filter by job ids
{
    "jobIds": 
    [
      "a7bd3e1b-****-****-****-243c4df89a2d"
    ]
}
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the created baseline id displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "data": [
        {
            "jobId": "a7bd3e1b-****-****-****-243c4df89a2d",
            "type": 1,
            "status": 2
        }
    ],
    "metadata": {
        "pageIndex": 1,
        "pageSize": 5,
        "totalCount": 1
    }
}