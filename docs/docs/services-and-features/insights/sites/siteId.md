# Retrieve Site ID

This API method (`/insights/sites/{siteUrl}/siteId` navigation property) allows users to retrieve the site ID for a specific SharePoint site URL. This method is useful for obtaining the unique identifier of a site.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/sites/{siteUrl}/siteId` | insights.graph.readwrite.all |

## Request

This section outlines the HTTP method and endpoint used to export site ID. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/sites/{siteUrl}/siteId` | Retrieves the site ID. |

### Query Parameters

The API supports a single query parameter to specify the site URL for which the site ID is being requested.

| Parameter | Description            | Type    | Required? |
|-----------|------------------------|---------|-----------|
| siteUrl   | SharePoint site URL    | string  | Yes       |

## Responses

The API response provides detailed information about the site ID retrieved. 

| Elements | Description                        | Type    |
|----------|------------------------------------|---------|
| status   | The HTTP response status code      | integer |
| message  | The error message                  | string  |
| values   | A list of site ID objects       | list   |

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant site IDs in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the Insights for Microsoft 365 environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/insights/sites/https%3A%2F%2F****market.sharepoint.com%2Fsites%2Fland2/siteid
```

## Response Sample

The following response returns the site ID for the specified Site URL in a structured format. 

```json
{
  "values": [
    "49cb49cb-49cb-49cb-49cb-49cb49cb49cb49cb"
  ],
  "status": 200,
  "message": "",
  "nextLink": null
}
```