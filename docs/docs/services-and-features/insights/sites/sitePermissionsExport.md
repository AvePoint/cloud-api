# Export Site Permissions

This API method (`/insights/sites/permission/export` navigation property) allows users to export the permission report for specific site collections. This method is useful for obtaining detailed insights into the permissions granted to site collections within a specified time range.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/sites/permission/export` | insights.graph.readwrite.all |

## Request

This section outlines the HTTP method and endpoint used to export site permissions. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/sites/permission/export` | Exports the site permissions. |


## Query Parameters

The API supports several query parameters to refine and customize the data export. These parameters allow users to specify the site URLs to filter the results effectively.

| Parameter | Description | Type    | Required? |
|-----------|-------------|---------|-----------|
| siteUrls  | Sets the URLs of site collections for which you want to get the permission related information. No more than 100 site collections in the list | list   | Yes       |


## Responses

The API response provides export job ID for exporting and downloading the site permissions report. You can use the Jobs resource to check the export job progress and export the report file. For details, see [Jobs](/insights/exportJobs/exportJobFile.md).

| Elements  | Description | Type    |
|-----------|-------------|---------|
|jobId	 | The job ID	| string |
|status |	The HTTP response status code |	integer|
|message |	The error message |	string|



## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. 

```json
 https://graph-us.avepointonlineservices.com/insights/sites/permission/export?siteUrls=https%3A%2F%2Fm365x353634.sharepoint.com%2Fsites%2Fretail&siteUrls=https%3A%2F%2Fm365x353634.sharepoint.com%2Fsites%2Fsite0
```

## Response Sample

The following is a sample response for this API method, which includes export job ID of the site permission report and its operation status 

```json
{
  "jobId": "67890",
  "status": 200,
  "message": ""
}
```