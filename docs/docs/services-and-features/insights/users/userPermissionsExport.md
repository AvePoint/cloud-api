# Export User Permissions

This API method (`/insights/users/{email}/access/export` navigation property) allows users to export the access reports of specific users in different workspaces. This method is useful for obtaining detailed insights into the permissions granted to users within a specified time range. 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/users/{email}/access/export` |insights.graph.readwrite.all  |

## Request 

This section outlines the HTTP method and endpoint used to export user access reports. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/users/{email}/access/export` | Exports the user access report. |


## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify the site URLs, emails, and next link to filter the results effectively.


| Parameter  | Description                                                                 | Type   | Required? |
|------------|-----------------------------------------------------------------------------|--------|-----------|
| email| Sets the email addresses or loginName of users for which you want to export the permission report. | string | Yes |
| exportOptionType | Export options: **1** - summary and site collection level access report, **2** - summary and access report to all objects, **3** - summary report only | integer | Yes | 
| siteUrls | Sets the URLs of site collections for which you want to export the permission report | list | No | 
| dataSources | Sets the workspace in which you want to export the access report of users. Multiple values are allowed. (e.g., **Microsoft Teams**, **SharePoint Online**, **OneDrive**, **Microsoft 365 Group**) | list | Yes |


### Responses

The API response provides detailed information about the export job. 

| Elements	| Description	|Type|
|---|--- |---|
|jobId	 | The job ID	| string |
|status |	The HTTP response status code |	integer|
|message | error message | string |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant permission details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the Insights for Microsoft 365 environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/insights/users/insightstester001_jasoninsightstest.onmicrosoft.com%2523ext%2523%2540m365x636363.onmicrosoft.com/access/export?exportOptionType=2&siteUrls=https%3A%2F%2Fm365x636363.sharepoint.com%2Fsites%2Fjuly2022publicteam01&dataSources=microsoft%20teams&dataSources=sharepoint%20online
```

## Response Sample  

The following is a sample response for this API method, which includes export job ID of the user access report and its operation status 

```json
{
  "jobId": "67890",
  "status": 200,
  "message": "OK"
}
```