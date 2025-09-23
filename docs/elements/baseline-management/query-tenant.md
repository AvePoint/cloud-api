# Query Tenants

Use this API to query tenants registered in the Baseline Management module. Supports optional filtering by tenant IDs and pagination.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/tenants/batch` | elements.bm.tenant.read.all or elements.bm.tenant.readwrite.all |  

## Request

This section provides details on the HTTP method and endpoint used to query baselines.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/bm/tenants/batch` | Query all tenants with optional filtering and pagination. |

## Query Parameters

You can use the following optional query parameters in the URL to control pagination:

|Parameter|Description | Type|Required?|
|---|---|---|---|
|pageIndex|The index of the page to retrieve (starting from 1). |int|No|
|pageSize|The number of records to return per page. The default value is 50. Acceptable range is from 1 to 100.|int|No|

## Request Body Parameters

You can provide a list of tenant id in the request body to filter the results. This field is optional.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|tenantIds|The ID of the tenant. |array of string|No|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the created baseline id displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| tenantName | The **Name** of the tenant. | string |
| status | The **Status** of the baseline.<ul><li>**1** Connected</li><li>**2** Deployed with exception</li><li>**3** Deploying</li><li>**4** Deployment draft saved</li><li>**5** Deployment failed </li><li>**6** Expired</li><li>**7** Deployed </li><li>**8** Restore failed </li><li>**19** Restored</li><li>**10** Restored with exception</li><li>**11** Restoring</li><li>**12** Retrieving setting</li><li>**13** Review deployment</li><li>**14** Review restore</li><li>**15** Scheduled deployment </li><li>**16** Schedule restore</li><li>**17** Settings retrieval failed</li></ul> | int |
| driftDetected | The count of drift detected. | int |
| driftDetectedTime | The last drift detected date (UTC). | string |
| lastDeployedTime | The last deploy date (UTC). | string |
| customerId | The Id of customer. | string |
| tenantId | The Id of tenant. | string |
| autoAlignmentStatus | The status of Auto-Alignment. <ul><li>**0** Disable</li><li>**1** Enable</li></ul>| string |
| appliedBaselines | The baselines that applied to the tenant.| string |
| baselineId | The id of baseline.| string |
| baselineName | The name of baseline.| string |
| version | The version of baseline.| int |

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/bm/baselines/batch?pageIndex=1&pageSize=50

{
    "tenantIds": 
    [
      "af83b8e1-****-****-****-970f92192dc5"
    ]
}
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the created baseline id displayed in the response body. For more details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "data": [
        {
            "tenantName": "2****l",
            "status": 5,
            "driftDetected": 51,
            "driftDetectedTime": "2025-09-05T10:30:00Z",
            "customerId": "ce43e186-****-****-****-86b51b0aef92",
            "tenantId": "af83b8e1-****-****-****-970f92192dc5",
            "autoAlignmentStatus": 1,
            "lastDeployedTime": "2025-09-11T02:26:34Z",
            "appliedBaselines": [
                {
                    "baselineId": "de473862-****-****-****-3a1c20398d55",
                    "baselineName": "baseline1",
                    "version": "4"
                }
            ]
        }
    ],
    "metadata": {
        "pageIndex": 1,
        "pageSize": 5,
        "totalCount": 1
    }
}