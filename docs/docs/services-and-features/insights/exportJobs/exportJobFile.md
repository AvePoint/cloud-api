# Download Export Job File

This API method (`/insights/job/{jobId}/exportfile` navigation property) allows users to download the report file of an export job. This method is useful for downloading the exported report of an export job using its job ID.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/job/{jobId}/exportfile` | insights.graph.readwrite.all |

## Request

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. This will return a ZIP file with the relevant report file in XLSX format, enabling easy integration with other systems or applications.

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/job/{jobId}/exportfile` | Download the report file of an export job. |

## Query Parameters

The API supports a single query parameter to specify the job ID for which the report file is being requested.

| Parameter | Description | Type    | Required? |
|-----------|-------------|---------|-----------|
| jobId     | Job ID     | integer | Yes       |

## Responses

If successful, this API response returns the report file for downloading.  

## Request Sample

In Postman, you can send this `GET` request and select **Send and Download** to retrieve this report file. The following request is an API call to the Insights for Microsoft 365 environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/insights/job/169/exportfile
```

## Response Sample

This API response returns the report file in ZIP.