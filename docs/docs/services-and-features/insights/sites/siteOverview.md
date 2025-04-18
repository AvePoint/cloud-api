# Retrieve Sites Overview

This API method (`/insights/sites/overview` navigation property) allows users to retrieve risk level overview for specific sites. This method is useful for obtaining a summary of site risk level properties and statuses.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/sites/overview` | insights.graph.readwrite.all|  



## Request

This section outlines the HTTP method and endpoint used to retrieve the site overview on risk levels. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/sites/overview` | Retrieves the site overview on risk levels. |



## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify the risk level and next link to filter the results effectively.

| Parameter | Description                              | Type    | Required? |
|-----------|------------------------------------------|---------|-----------|
| riskLevel | Specifies the set of risk levels.            | list   | No        |
| nextLink  | Sets the number of results for one page. 100 results on one page at most. | string  | No        |

## Responses

The API response provides detailed information about the sites retrieved. Each site in the response includes various attributes that describe its properties and status. 

| Elements | Description                        | Type    |
|----------|------------------------------------|---------|
| status   | The HTTP response status code      | integer |
| message  | The error message                  | string  |
| nextLink | The token to be used to get the remaining results of this request | string  |
| values   | A list of site overview objects | list   |

**Site overview**

| Elements | Description                        | Type    |
|----------|------------------------------------|---------|
| siteName           | Name of the SharePoint site           |     string   |
| siteUrl            | URL of the SharePoint site                            |   string   |
| riskItemCount      | Number of risk items associated with the site         | integer|
| sensitiveItemCount | Number of sensitive items associated with the site    | integer|
| exposureItemCount  | Number of exposure items associated with the site     | integer|  

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant site overview details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the Insights for Microsoft 365 environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/insights/sites/overview?riskLevel=1&riskLevel=2&riskLevel=3&nextLink=12313
```

## Response Sample

The following response provide the overview for the sites that meets the specified risk levels.

```json
{
    "values": [  // list of site overview objects
        {
          "siteName": "SPO Site",  // Name of the SharePoint site
          "siteUrl": "https://ja****alita.sharepoint.com/sites/sposite",  // URL of the SharePoint site
          "riskItemCount": 25,  // Number of risk items associated with the site
          "sensitiveItemCount": 25,  // Number of sensitive items associated with the site
          "exposureItemCount": 27  // Number of exposure items associated with the site
        }
      ],
    "status": 200,  // HTTP status code indicating the request was successful
    "message": "",  // Message field, currently empty
    "nextLink": null  // Link to the next set of results, null if there are no more results
}