# Add Tag to Specific Object

This API method (`/insights/sites/{siteId}/{objectUrl}/settag` navigation property) allows users to add tag to a specific object. This method is useful for categorizing objects with tags that are commonly used in Insights. 

[only for object]: # 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/sites/{siteId}/{objectUrl}/settag` | insights.graph.readwrite.all |

[all the methods are GET, why do you need write permission?  -confirmed, cannot be changed as this has been in use for a few releases now ]: #

## Request 

This section outlines the HTTP method and endpoint used to retrieve job information. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| PATCH | `/insights/sites/{siteId}/{objectUrl}/settag` | Adds a tag to a specific object. |


## Query Parameters

The API supports several query parameters to specify the object to which the tag will be added.

| Parameter   | Description                                      | Type   | Required? |
|-------------|--------------------------------------------------|--------|-----------|
| siteId        | Sets the ID of the site where the object resides.                                 | string | Yes       |
| objectUrl   | Sets the URL of the object  to which the tag you want to add.   | string | Yes        |
| tagName  | Sets the name of the tag in Inisights that you want to add to the object.  | string | Yes        |



## Responses

The API response provides detailed information about the tag status.  

| Elements | Description                                      | Type    |
|----------|--------------------------------------------------|---------|
| status | The status of the tag action.                                                 | integer  |
| message | The error message if the tag action failed.                   | string |


## Request Sample

To use this API, send a `PATCH` request to the specified endpoint, including necessary parameters as defined. The following request is an API call to the Insights environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/insights/sites/5794af14-b6ee-4194-b122-bdaa1a******/https%3A%2F%2******markettest.sharepoint.com%2Fsites%2Fharland2/settag?tagName=FalsePositive
```

## Response Sample  

The following is a sample response for this API method, which includes the action result and details. 

```json
{
  "status": 200, // current operation status
  "message": "" // error message if this API method failed.
}