# Export Permission-Related Information for Sharing Links 

This API method (`/insights/sharingLinks/export` navigation property) allows users to export permission-related information for sharing links. This method is useful for obtaining detailed insights into the permissions granted to links within a specific time range.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/sharingLinks/export` | insights.graph.readwrite.all |


## Request

This section outlines the HTTP method and endpoint used to export permission-related information for sharing links. It provides a concise description of the action performed by the API call.

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/sharingLinks/export` | Exports the permissions-related information for sharing links. |


## Query Parameters

The API supports several query parameters to refine and customize the data export. These parameters allow users to specify link types and time range to filter the results effectively.

| Parameter | Description            | Type    | Required? |
|-----------|------------------------|---------|-----------|
| exportLinkType | Sets export type: <ul><li>**32** for Flexible link</li><li> **64** for Organization link</li><li> **128** for Anonymous link</li> | integer | Yes |   
| startTime | Filter by time, time format: yyyy-MM-ddTHH:mm:ss | string | Yes |   
| finishTime | Filter by time, time format: yyyy-MM-ddTHH:mm:ss | string | Yes | 

## Responses

The API response provides detailed information about the export job. You can use the Jobs resource to check the export job progress and export the report file. For details, see [Jobs](../exportJobs/exportJobFile.md).

| Elements	| Description	|Type|
|---|--- |---|
|jobId	 | The job ID	| string |
|status |	The HTTP response status code |	integer|
|message |	The error message |	string|



## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined. The following request is an API call to the Insights for Microsoft 365 environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/insights/sharingLinks/export?exportLinkType=32&startTime=2023-01-01T00:00:00&finishTime=2023-01-31T23:59:59
```

## Response Sample

The following is a sample response for this API method, which includes export job ID of the permission report for sharing links nd its operation status 

```json
{
  "jobId": "12345",
  "status": 200,
  "message": ""
}