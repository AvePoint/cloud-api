# Retrieve Tenant Information

Use this API to retireve the general information of tenants added to the Baseline Management module.

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../register-app.md).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/tenants/batch` | elements.bm.tenant.read.all or elements.bm.tenant.readwrite.all |  

## Request

This section provides details on the HTTP method and endpoint used to retireve the general information of tenants added to the Baseline Management module.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/partner/external/v3/bm/tenants/batch` | Retireves the general information of tenants added to the Baseline Management module. |

## Query Parameters

You can use the following optional query parameters in the URL to control pagination:

|Parameter|Description | Type|Required?|
|---|---|---|---|
|pageIndex|The index of the page to retrieve. The default value is 1. |integer|No|
|pageSize|The number of records to return per page. The default value is 50, and the acceptable range is from 1 to 100.|integer|No|

## Request Body Parameters

You can provide a list of tenant IDs in the request body to filter the results. This is optional.

|Parameter|Description | Type|Required?|
|---|---|---|---|
|tenantIds|The IDs of the tenants. |string[] |No|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the general information of tenants added to the Baseline Management module  displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| tenantName | The name of the tenant. | string |
| status | The status of the tenant.<ul><li>**1** - Connected</li><li>**2** - Deployed with exception</li><li>**3** - Deploying</li><li>**4** - Deployment draft saved</li><li>**5** - Deployment failed </li><li>**6** - Expired</li><li>**7** - Deployed </li><li>**8** - Restore failed </li><li>**19** - Restored</li><li>**10** - Restored with exception</li><li>**11** - Restoring</li><li>**12** - Retrieving setting</li><li>**13** - Review deployment</li><li>**14** - Review restore</li><li>**15** - Scheduled deployment </li><li>**16** - Schedule restore</li><li>**17** - Settings retrieval failed</li></ul> | integer |
| driftDetected | The number of configuration deviations that have been detected for the tenant. | integer |
| driftDetectedTime | The time (UTC) when configuration deviations were detected. | string |
| lastDeployedTime | The time (UTC) when the baseline was deployed to the tenant. | string |
| customerId | The ID of the customer. | string |
| tenantId | The ID of the tenant. | string |
| autoAlignment | The status of the auto-alignment setting. <ul><li>**0** - Disabled</li><li>**1** - Enabled</li></ul>| string |
| appliedBaselines | The baselines that have been deployed to the tenant.| string |
| baselineId | The ID of the baseline.| string |
| baselineName | The name of the baseline.| string |
| version | The version of the baseline.| integer |

## Request Sample

To use this API, send a POST request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/bm/baselines/batch?pageIndex=1&pageSize=50

{
    "tenantIds": 
    [
      "af83b8e1-****-****-****-970f92192dc5" // The ID of the tenant
    ]
}
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the general information of tenants added to the Baseline Management module displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../Use-AvePoint-Graph-API.md#http-status-code).

```json
{
    "data": [
        {
            "tenantName": "2****l", // The name of the tenant
            "status": 5, // The status of the tenant. 5 represents "Deployment failed"
            "driftDetected": 51, // The number of configuration deviations that have been detected for the tenant
            "driftDetectedTime": "2025-09-05T10:30:00Z", // The time (UTC) when configuration deviations were detected
            "customerId": "ce43e186-****-****-****-86b51b0aef92", // The ID of the customer
            "tenantId": "af83b8e1-****-****-****-970f92192dc5", // The ID of the tenant
            "autoAlignment": 1, // The status of the auto-alignment setting. 1 represents "Enabled"
            "lastDeployedTime": "2025-09-11T02:26:34Z", // The time (UTC) when the baseline was deployed to the tenant
            "appliedBaselines": [
                {
                    "baselineId": "de473862-****-****-****-3a1c20398d55", // The ID of the baseline
                    "baselineName": "baseline1", // The name of the baseline
                    "version": "4" // The version of the baseline
                }
            ]
        }
    ],
    "metadata": {
        "pageIndex": 1, // The page index of the current request
        "pageSize": 50, // The number of tenants to be retrieved in one request
        "totalCount": 1 // The total number count that matches the request
    }
}