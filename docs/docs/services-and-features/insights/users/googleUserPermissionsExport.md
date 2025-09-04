# Export Google User Permissions

This API method (`/insights/google/users/{email}/access/export` navigation property) allows users to export the access reports of specific Google users in different workspaces. This method is useful for obtaining detailed insights into the permissions granted to Google users. 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/google/users/{email}/access/export` |insights.graph.readwrite.all  |

## Request 

This section outlines the HTTP method and endpoint used to export google user access reports. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/google/users/{email}/access/export` | Exports the Google user access report. |


## Query Parameters

The API supports several query parameters to refine and customize the data export. These parameters allow users to specify the drive Ids, email addresses, and data sources to filter the results effectively.


| Parameter  | Description                                                                 | Type   | Required? |
|------------|-----------------------------------------------------------------------------|--------|-----------|
| email| Sets the primary email addresses of Google users for whom you want to export the permission report. | string | Yes |
| driveIds | Sets the IDs of Google drives for which you want to export the permission report. | list | No | 
| dataSources | Sets the workspace in which you want to export the access report of users. Multiple values are allowed. (e.g., **My Drive**, **Shared Drive**)| list | Yes |


## Responses

The API response provides the export job ID and its operation status. You can use the Jobs resource to check the export job progress and export the report file. For details, see [Jobs](../exportJobs/exportJobFile.md).

| Elements	| Description	|Type|
|---|--- |---|
|jobId	 | The job ID	| string |
|status |	The HTTP response status code |	integer|
|message | error message | string |

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. The following request is an API call to the Insights environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/insights/google/users/insights***and**@avepoint*****.com/access/export?exportOptionType=2&driveIds=0ALUvlYxwVLhSUk9PVA&dataSources=shared%20drive&dataSources=my%20drive
```

## Response Sample  

The following is a sample response for this API method, which includes export job ID of the user access report and its operation status. 

```json
{
  "jobId": "67891",
  "status": 200,
  "message": ""
}