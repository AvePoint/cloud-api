# Export Activities for a Specific Object

Export the activity report for a specific object. By invoking the `/insights/activities/object/{path}/export` endpoint, you can retrieve the activities performed on a specific object. This method is useful for obtaining detailed insights into the activities performed on an object within a specific time range. 

[only for object]: # 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/activities/object/{path}/export` | insights.graph.readwrite.all |

[all the methods are GET, why do you need write permission?  -confirmed, cannot be changed as this has been in use for a few releases now ]: #

## Request 

This section outlines the HTTP method and endpoint used to retrieve job information. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/activities/object/{path}/export` | Exports the activities performed on a specific object. |


## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify object, time ranges, and event types to filter the results effectively.

| Parameter   | Description                                      | Type   | Required? |
|-------------|--------------------------------------------------|--------|-----------|
| path        | The object URL.                                 | string | Yes       |
| startTime   | The start time of the reporting time range, in ISO 8601 format.  | string | No        |
| finishTime  | The finish time of the reporting time range, in ISO 8601 format. | string | No        |
| eventTypes  | Filter by event type                             | list  | No        |


## Responses

If successful, the API response will provide the export job ID. You can use the Jobs resource to check the export job progress and export the report file. For details, see [Jobs](/insights/exportJobs/exportJobFile.md). 

| Elements | Description                                      | Type    |
|----------|--------------------------------------------------|---------|
| jobId    | The job ID of activity report.                                      | string  |
| status   | The status for exporting activity report.                   | integer |
| message  | The error message if the job failed.                                 | string  |

## Request Sample


```json
https://graph-us.avepointonlineservices.com/insights/activities/object/https%3A%2F%2Falitamarkettest.sharepoint.com%2Fsites%2Fharlandleteams001/export?startTime=2024-12-03T00%3A00%3A00&finishTime=2025-01-09T00%3A00%3A00&eventTypes=ListViewed&eventTypes=ListItemViewed
```

## Response Sample  

This API response returns the export job ID for downloading the activity report. 

```json
{
  "jobId": "4790",
  "status": 200, // current operation status
  "message": "" // error message if this API method failed.
}
```