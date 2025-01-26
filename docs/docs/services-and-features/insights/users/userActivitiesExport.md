# Export User Activities

This API method (`/insights/users/{email}/activities/export` navigation property) allows users to export the activity data for a specific user. This method is useful for obtaining detailed insights into the user activities within a specified time range. 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/users/{email}/activities/export` |  insights.graph.readwrite.all |

## Request 

This section outlines the HTTP method and endpoint used to export the activity data for a specific user. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/users/{email}/activities/export` | Exports the activity data for a specific user. |


## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify the email, time ranges, and event types to filter the results effectively.

| Parameter   | Description                                      | Type   | Required? |
|-------------|--------------------------------------------------|--------|-----------|
| email     | Filter by email                                  | string | Yes       |
| startTime| Filter by start time, Time format: yyyy-MM-ddTHH:mm:ss | string | No        |
| finishTime| Filter By finish time, Time format: yyyy-MM-ddTHH:mm:ss | string | No        |
| eventTypes| Filter by event type                             | list  | No        |


### Responses

The API response provides detailed information about the export job. You can use the Jobs resource to check the export job progress and export the report file. For details, see [Jobs](/insights/exportJobs/exportJobFile.md).

| Elements	| Description	|Type|
|---|--- |---|
|jobId	 | The job ID	| string |
|status |	The HTTP response status code |	integer|
|message | error message | string |

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. This will return the export job ID and operation status.

```json
https://graph-us.avepointonlineservices.com/insights/users/insightstester001_jasoninsightstest.onmicrosoft.com%2523ext%2523%2540m365x636363.onmicrosoft.com/activities/export?startTime=2023-01-01T01%3A37%3A57&finishTime=2023-04-01T01%3A37%3A57&eventTypes=ListViewed&eventTypes=ListItemViewed
```

## Response Sample  

The following is a sample response for this API method, which includes export job ID of the user activity report and its operation status 

```json
{
  "jobId": "67890",
  "status": 200,
  "message": ""
}
```