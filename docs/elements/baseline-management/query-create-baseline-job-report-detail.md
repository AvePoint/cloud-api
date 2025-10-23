# Retrieve Baseline Creation Job Report

Use this API to retrieve the report details of a baseline creation job.

## Permission  

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../register-app.md).  

| API  | Permission  |
|-----------|--------|
| `/partner/external/v3/bm/baselines/{baselineId}/reports` | elements.bm.baseline.read.all or elements.bm.baseline.readwrite.all |  

## Request

This section provides details on the HTTP method and endpoint used to retrieve the report details of a baseline creation job.

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/partner/external/v3/bm/baselines/{baselineId}/reports` | Retrieves the report details of a baseline creation job. |

## URL Parameters

This section describes the query parameters that can be added to the URL when sending a GET request.

| Parameter | Description | Type | Required |
| --- | --- | --- |---|
| baselineId | The ID of the baseline. | string | Yes |

## Query Parameters

You can use the following optional query parameters in the URL to control pagination:

|Parameter|Description | Type|Required?|
|---|---|---|---|
|pageIndex|The starting number of the page to get the report details. The default value is 1|integer|No|
|pageSize|The number of objects to display on one page. The default value is 50 and the maximum value allowed is 100.|integer|No|

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
https://graph-us.avepointonlineservices.com/partner/external/v3/bm/baselines/23351ee7-****-78n6-****-e8e3ffc29cd7/reports?pageIndex=1&pageSize=50
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
        "pageIndex": 1, // The current display page
        "pageSize": 50, // The number of objects on the display page
        "totalCount": 109 // The total number of objects matching the query parameters
    }
}