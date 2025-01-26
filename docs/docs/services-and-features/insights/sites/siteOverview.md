# Retrieve Sites Overview

The `/insights/sites/overview` API method allows users to retrieve risk level overview for specific sites. This method is useful for obtaining a summary of site risk level properties and statuses.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/sites/overview` | insights.graph.readwrite.all|  



## Request

This section outlines the HTTP method and endpoint used to retrieve the site overview on risk levels. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/sites/overview` | Retrieves the site overview on risk levels. |



### Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify the risk level, next link, and other criteria to filter the results effectively.

| Parameter | Description                              | Type    | Required? |
|-----------|------------------------------------------|---------|-----------|
| riskLevel | Enter the set of risk levels.            | list   | No        |
| nextLink  | Sets the number of results for one page. 100 results on one page at most. | string  | No        |

## Responses

The API response provides detailed information about the sites retrieved. Each site in the response includes various attributes that describe its properties and status.

| Elements | Description                        | Type    |
|----------|------------------------------------|---------|
| status   | The HTTP response status code      | integer |
| message  | The error message                  | string  |
| nextLink | The token to be used to get the remaining results of this request | string  |
| values   | A list of site overview objects | list   |

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant site overview details in a structured format, enabling easy integration with other systems or applications.  

```json
https://graph-us.avepointonlineservices.com/insights/sites/overview?riksLevel=1&rikLevel=2&rikLevel=3&nextLink=12313
```

## Response Sample

The following response provide the overview for the sites that meets the specified risk levels.

```json
{
    "values": [
        {
          "siteName": "SPO Site 001",
          "siteUrl": "https://ja****alita.sharepoint.com/sites/sposite001",
          "riskItemCount": 25,
          "sensitiveItemCount": 25,
          "exposureItemCount": 27
        }
      ],
    "status": 200,
    "message": "",
    "nextLink": null
}
```