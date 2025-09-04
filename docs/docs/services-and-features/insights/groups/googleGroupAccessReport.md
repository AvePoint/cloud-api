# Export Google Group Access Report

Export the permission-related information of specific groups. By invoking the `/insights/google/groups/{groupId}/access/export` endpoint, you can export the access report for specific Google groups. This method is useful for obtaining detailed insights into the permissions granted to Google groups. 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/google/groups/{groupId}/access/export` |insights.graph.readwrite.all   |

## Request 

This section outlines the HTTP method and endpoint used to retrieve Google group access report. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/google/groups/{groupId}/access/export` | Exports the Google group access report. |


## Query Parameters

The API supports several query parameters to refine and customize the data export. These parameters allow users to specify the group ID, data sources, export options, and drive Ids to filter the results effectively.


| Parameter        | Description     | Type    | Required? |
|------------------|----------------|---------|-----------|
| groupId          | Sets the group email for which you want to export the permission report. Note that if you want to export the permission report for all groups, skip this parameter and ensure the exportOptionType parameter is set to **3**. | string  | Yes       |
| exportOptionType | Export options: <ul><li>**1** for summary and google drive level access report (not supported yet)</li><li> **2** for summary and access report to all objects</li><li> **3** - summary report only</li> | integer | Yes        |
| driveIds         | Sets the IDs of Google drives for which you want to export the permission report.                             | list   | No        |
| dataSources      | Sets the workspace in which you want to export the access report of users. Multiple values are allowed, such as **User Drive**, **Shared Drive**.          | list   | Yes        |
<!---| language | Sets the display language for the access report. Supported values are: **en-US**, **ja-JP**, and **fr-FR**. | string | No --->


[languages + data source rewrite]: #

## Responses

The API response provides the export job ID and its operation status. You can use the Jobs resource to check the export job progress and export the report file. For details, see [Jobs](../exportJobs/exportJobFile.md).

| Elements | Description                                      | Type    |
|----------|--------------------------------------------------|---------|
| jobId    | The job ID                                       | string  |
| status   | The HTTP response status code                    | integer |
| message  | The error message                                | string  |


## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined. This will return the export job ID for checking the job status and downloading the report file. The following request is an API call to the Insights environment in the US - East region. 

```json
https://graph-us.avepointonlineservices.com/insights/google/groups/insightgroup***dev@avepoint*****.com/access/export?exportOptionType=2&driveIds=0AGS***TS_s2****PVA&dataSources=shared%20drive
```


## Response Sample  

The following is a sample response for this API method, which includes export job ID of the permission report and its operation status 

```json
{
    "jobId": "3802",
    "status": 200,
    "message": ""
}