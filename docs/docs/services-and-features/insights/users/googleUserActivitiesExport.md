# Export Google User Activities

This API method (`/insights/google/users/{email}/activities/export` navigation property) allows users to export the activity data for a specific user. This method is useful for obtaining detailed insights into the Google user activities within a specified time range. 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/google/users/{email}/activities/export` |  insights.graph.readwrite.all |

## Request 

This section outlines the HTTP method and endpoint used to export the activity data for a specific google user. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/google/users/{email}/activities/export` | Exports the activity data for a specific Google user. |


## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify the email, time ranges, and event types to filter the results effectively.

| Parameter   | Description                                      | Type   | Required? |
|-------------|--------------------------------------------------|--------|-----------|
| email     | Filter by email                                  | string | Yes       |
| startTime| Filter by start time, Time format: yyyy-MM-ddTHH:mm:ss | string | No        |
| finishTime| Filter By finish time, Time format: yyyy-MM-ddTHH:mm:ss | string | No        |
| eventTypes| Filter by event type                             | list  | No        |


## Responses

The API response provides detailed information about the export job. You can use the Jobs resource to check the export job progress and export the report file. For details, see [Jobs](../exportJobs/exportJobFile.md).

| Elements	| Description	|Type|
|---|--- |---|
|jobId	 | The job ID	| string |
|status |	The HTTP response status code |	integer|
|message | error message | string |

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. This will return the export job ID and operation status. The following request is an API call to the Insights environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/insights/google/users/insights***and**@avepoint*****.com/activities/export?startTime=2025-05-01T01%3A37%3A57&finishTime=2025-10-01T01%3A37%3A57&eventTypes=create&eventTypes=label_added
```

## Response Sample  

The following is a sample response for this API method, which includes export job ID of the google user activity report and its operation status. 

```json
{
  "jobId": "67891",
  "status": 200,
  "message": ""
}