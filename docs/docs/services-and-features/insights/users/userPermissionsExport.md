# Export User Permissions

This API method (`/insights/users/{email}/access/export` navigation property) allows users to export the access reports of specific users in different workspaces. This method is useful for obtaining detailed insights into the permissions granted to users. 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/users/{email}/access/export` |insights.graph.readwrite.all  |

## Request 

This section outlines the HTTP method and endpoint used to export user access reports. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/users/{email}/access/export` | Exports the user access report. |


## Query Parameters

The API supports several query parameters to refine and customize the data export. These parameters allow users to specify the site URLs, email addresses, and data sources to filter the results effectively.


| Parameter  | Description                                                                 | Type   | Required? |
|------------|-----------------------------------------------------------------------------|--------|-----------|
| email| Sets the email addresses or loginName of users for which you want to export the permission report. | string | Yes |
| exportOptionType | Export options: <ul><li>**1** for summary and site collection level access report</li><li> **2** for summary and access report to all objects</li> <li>**3** for summary report only</li> | integer | Yes | 
| siteUrls | Sets the URLs of site collections for which you want to export the permission report | list | No | 
| dataSources | Sets the workspace in which you want to export the access report of users. Multiple values are allowed. (e.g., **Microsoft Teams**, **SharePoint Online**, **OneDrive**, **Microsoft 365 Group**) | list | Yes |


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
https://graph-us.avepointonlineservices.com/insights/users/insights******001_j*****insightstest.onmicrosoft.com%2523ext%2523%2540m3********.onmicrosoft.com/access/export?exportOptionType=2&siteUrls=https%3A%2F%2Fm******.sharepoint.com%2Fsites%2Fjuly2022public****01&dataSources=microsoft%20teams&dataSources=sharepoint%20online
```

## Response Sample  

The following is a sample response for this API method, which includes export job ID of the user access report and its operation status. 

```json
{
  "jobId": "67890",
  "status": 200,
  "message": ""
}