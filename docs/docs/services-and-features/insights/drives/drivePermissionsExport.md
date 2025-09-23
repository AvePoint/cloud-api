# Export Drive Permissions

This API method (`/insights/google/drives/permission/export` navigation property) allows users to export the permission report for specific Google drives. This method is useful for obtaining detailed insights into the permissions granted to Google drives within a specified time range.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/google/drives/permission/export` | insights.graph.readwrite.all |

## Request

This section outlines the HTTP method and endpoint used to export drive permissions. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/google/drives/permission/export` | Exports the drive permissions. |


## Query Parameters

The API supports several query parameters to refine and customize the data export. These parameters allow users to specify the drive IDs to filter the results effectively.

| Parameter | Description | Type    | Required? |
|-----------|-------------|---------|-----------|
| driveIds  | Sets the IDs of Google drives for which you want to get the permission related information. No more than 100 Google drives in the list. | list   | Yes       |


## Responses

The API response provides export job ID for exporting and downloading the drive permissions report. You can use the Jobs resource to check the export job progress and export the report file. For details, see [Jobs](../exportJobs/exportJobFile.md).

| Elements  | Description | Type    |
|-----------|-------------|---------|
|jobId	 | The job ID	| string |
|status |	The HTTP response status code |	integer|
|message |	The error message |	string|



## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. The following request is an API call to the Insights environment in the US - East region.

```json
 https://graph-us.avepointonlineservices.com/insights/google/drives/permission/export?driveIds=0AG****TS_s2E***PVA&driveIds=insightsdev*****@avepoint***.com
```

## Response Sample

The following is a sample response for this API method, which includes export job ID of the drive permission report and its operation status. 

```json
{
  "jobId": "67891",
  "status": 200,
  "message": ""
}