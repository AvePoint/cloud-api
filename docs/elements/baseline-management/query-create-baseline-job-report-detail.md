# Retrieve Baseline Creation Job Report

Use this API to retrieve the report details of a baseline creation job.

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../register-app.md).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/baselines/{baselineId}/reports` | elements.bm.baseline.read.all or elements.bm.baseline.readwrite.all |  

## Request

This section provides details on the HTTP method and endpoint used to retrieve the report details of a baseline creation job.

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/partner/external/v3/bm/baselines/{baselineId}/reports` | Retrieves the report details of a baseline creation job. |

## Query Parameters

You can use the following optional query parameters in the URL to control pagination:

|Parameter|Description | Type|Required?|
|---|---|---|---|
|pageIndex|The index of the page to retrieve. The default value is 1. |integer|No|
|pageSize|The number of records to return per page. The default value is 50, and the acceptable range is from 1 to 100.|integer|No|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the report details of the queried baseline creation job displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| source | The source of the configuration. | string |
| configuration | The name of the configuration.  | string |
| status | The status of the configuration retrieval action. | string |
| details | The detailed information to be displayed when a configuration fails to be retrieved. | string |

## Request Sample

To use this API, send a GET request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/partner/external/v3/bm/baselines/23351ee7-****-****-****-e8e3ffc29cd7/reports?pageIndex=1&pageSize=50
```

## Response Sample  

If the request has been successfully processed, a 200 OK response will be returned along with the report details of the queried baseline creation job displayed in the response body. For more details on the HTTP status code, refer to [Http Status Code](../Use-AvePoint-Graph-API.md#http-status-code).

```json
{
    "data": [
        {
            "source": "Intune", // The source of the configuration
            "configuration": "DeviceCompliancePolicies > MacOSCompliancePolicy", // The name of the configuration
            "status": "Successful", // The status of the configuration retrieval action
            "details": null // The detailed information to be displayed when a configuration fails to be retrieved
        },
        {
            "source": "Intune",
            "configuration": "DeviceCompliancePolicies > Windows10/11CompliancePolicy",
            "status": "Successful",
            "details": null
        },
        ...
    ],
    "metadata": {
        "pageIndex": 1, // The page index of thecurrent request
        "pageSize": 50, // The number of baseline creation jobs to be retrieved in one request
        "totalCount": 109 // The total number count that matches the request
    }
}