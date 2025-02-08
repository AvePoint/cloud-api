# Export Group Access Report

Export the permission-related information of specific groups. By invoking the `/insights/groups/{groupId}/access/export` endpoint, you can export the access report for specific groups. This method is useful for obtaining detailed insights into the permissions granted to groups. 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/groups/{groupId}/access/export` |insights.graph.readwrite.all   |

## Request 

This section outlines the HTTP method and endpoint used to retrieve group access report. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/groups/{groupId}/access/export` | Exports the group access report. |


## Query Parameters

The API supports several query parameters to refine and customize the data export. These parameters allow users to specify the group ID, data sources, export options, and site URLs to filter the results effectively.


| Parameter        | Description     | Type    | Required? |
|------------------|----------------|---------|-----------|
| groupId          | Sets the group ID for which you want to export the permission report. Note that if you want to export the permission report for all groups, skip this parameter and ensure the exportOptionType is set to **3**. | string  | Yes       |
| exportOptionType | Export options: **1** - summary and site collection level access report, **2** - summary and access report to all objects, **3** - summary report only | integer | Yes        |
| siteUrls         | Sets the URLs of site collections for which you want to export the permission report.                             | list   | No        |
| dataSources      | Sets the workspace in which you want to export the access report of users. Multiple values are allowed, such as **Microsoft Teams**, **SharePoint Online**, **OneDrive**, **Microsoft 365 Group**.          | list   | Yes        |
<!---| language | Sets the display language for the access report. Supported values are: **en-US**, **ja-JP**, and **fr-FR**. | string | No --->

> [!NOTE] 
> The principal names corresponding to the 4 special groups, including Everyone, are as follows:  
>- The principal names for **Everyone** is ```c:0(.s|tru```
>- The principal names for **EveryoneExceptExternalUsers** is ```c:0-.f|rolemanager|spo-grid-all-users```
>- The principal names for **All Users (windows)** is ```c:0!.s|windows```
>- The principal names for **All Users (membership)** is ```c:0!.s|forms%3amembership```


[languages + data source rewrite]: #

### Responses

The API response provides the export job ID and its operation status. You can use the Jobs resource to check the export job progress and export the report file. For details, see [Jobs](../exportJobs/exportJobFile.md).

| Elements | Description                                      | Type    |
|----------|--------------------------------------------------|---------|
| jobId    | The job ID                                       | string  |
| status   | The HTTP response status code                    | integer |
| message  | The error message                                | string  |


## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined. This will return the export job ID for checking the job status and downloading the report file. The following request is an API call to the Insights for Microsoft 365 environment in the US - East region. 

```json
https://graph-us.avepointonlineservices.com/insights/groups/ec34726b-f692-424f-aaf0-f6a478a1b9fc7/access/export?exportOptionType=2&siteUrls=https%3A%2F***%2Fm3***x636363.sharepoint.com%2Fsites%2F*****2022publicteam01&dataSources=microsoft%20teams&dataSources=sharepoint%20online
```


## Response Sample  

The following is a sample response for this API method, which includes export job ID of the permission report and its operation status 

```json
{
    "jobId": "4802",
    "status": 200,
    "message": ""
}
```