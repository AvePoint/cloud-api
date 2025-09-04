# Export Activities for a Specific Google Object

This API method (`/insights/google/activities/object/{id}/export` navigation property) allows users to export the activity report for a specific Google object. This method is useful for obtaining detailed insights into the activities performed on an object within a specific time range. 

[only for object]: # 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/google/activities/object/{id}/export` | insights.graph.readwrite.all |

[all the methods are GET, why do you need write permission?  -confirmed, cannot be changed as this has been in use for a few releases now ]: #

## Request 

This section outlines the HTTP method and endpoint used to retrieve job information. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/google/activities/object/{id}/export` | Exports the activities performed on a specific Google object. |


## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify object, time ranges, and event types to filter the results effectively.

| Parameter   | Description                                      | Type   | Required? |
|-------------|--------------------------------------------------|--------|-----------|
| id        | The object ID.                                 | string | Yes       |
| startTime   | The start time of the reporting time range, in ISO 8601 format.  | string | No        |
| finishTime  | The finish time of the reporting time range, in ISO 8601 format. | string | No        |
| eventTypes  | Filter by event type                             | list  | No        |


## Responses

If successful, the API response will provide the export job ID. You can use the Jobs resource to check the export job progress and export the report file. For details, see [Jobs](../exportJobs/exportJobFile.md). 

| Elements | Description                                      | Type    |
|----------|--------------------------------------------------|---------|
| jobId    | The job ID of activity report.                                      | string  |
| status   | The status for exporting activity report.                   | integer |
| message  | The error message if the job failed.                                 | string  |

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined. The following request is an API call to the Insights environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/insights/google/activities/object/1SfizLNSDzc6xLEs*****8IEMZ13h***8jLbc/export?startTime=2025-01-01T00%3A00%3A00&finishTime=2025-01-31T00%3A00%3A00&eventTypes=create&eventTypes=label_added
```

## Response Sample  

The following is a sample response for this API method, which includes export job ID for downloading the activity report. 

```json
{
  "jobId": "4791",
  "status": 200, // current operation status
  "message": "" // error message if this API method failed
}