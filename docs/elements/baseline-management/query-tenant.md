# Query Tenants

Use this API to query tenants registered in the Baseline Management module. Supports optional filtering by tenant IDs and pagination.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/tenants/batch` | elements.bm.baseline.read.all|  

## Request

This section provides details on the HTTP method and endpoint used to query baselines.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/bm/tenants/batch` | Query all tenants with optional filtering and pagination. |

## Query Parameters

You can use the following optional query parameters in the URL to control pagination:

|Parameter|Description | Type|Required?|
|---|---|---|---|
|pageIndex|The index of the page to retrieve (starting from 1). |int|Yes|
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
| status | The **Status** of the baseline.<ul><li>**1** Connected</li><li>**3** Settings retrieval failed</li><li>**4** Retrieving settings</li><li>**5** Review deployment</li><li>**6** Deployment draft saved</li><li>**7** Scheduled deployment</li><li>**8** Deploying</li><li>**9** Monitoring</li><li>**10** Deployed with exception</li><li>**11** Deployment failed</li><li>**13** Review restore</li><li>**14** Restored</li><li>**15** Restoring</li><li>**16** Restored with exception</li><li>**17** Restore failed</li><li>**18** Scheduled restore</li><li>**100** Expired</li></ul> | int |
| driftDetected | The count of drift detected. | int |
| driftDetectedDate | The last drift detected date (UTC). | string |
| lastDeployed | The last deploy date (UTC). | string |

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
            "name": "2****l",
            "status": 5,
            "driftDetected": 51,
            "driftDetectedTime": "2025-09-05T10:30:00Z",
            "customerId": "ce43e186-****-****-****-86b51b0aef92",
            "tenantId": "af83b8e1-****-****-****-970f92192dc5",
            "lastDeployedTime": "2025-09-06T10:30:00Z"
        }
    ],
    "metadata": {
        "pageIndex": 1,
        "pageSize": 5,
        "totalCount": 1
    }
}