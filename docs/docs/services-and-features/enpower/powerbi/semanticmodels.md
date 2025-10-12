# Retrieve Semantic Model Details

Use this API to retrieve the semantic model details.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/powerbi/semanticemodeldetails` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve the semantic model details.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerbi/semanticemodeldetails` | Retrieves all your semantic model details | 

## Query Parameters

The API supports the following query parameter to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| tenant | The tenant in which the semantic models are retrieved. By default, data of all tenants are retrieved. | string | No |
|top| The number of semantic model details retrieved. | integer | No |

## Responses

The API response provides detailed information about the semantic models retrieved. Each semantic model in the response includes various attributes that describe its properties and status.

| Elements           | Description                                                           | Type   | 
|--------------------|-----------------------------------------------------------------------|--------|
|id| The semantic model unique identifier. | string |
|name| The semantic model name. | string |
|datasourceId| The data source's unique identifier. | string |
|datasourceType| The data source type. | string |
|isRefreshable| Whether the semantic model is refreshable.<br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br>| boolean |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/powerbi/semanticemodeldetails
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "semanticModelDetails": [
    {
      "id": "2ab3012e-3952-4cd0-****-40289dd3da05", // The semantic model unique identifier      
      "name": "" // The semantic model name
      "datasourceId": "b7b83ae1-a3be-4553-****-ba289d97cbdb" // The data source's unique identifier
      "datasourceType": "Extension" // The data source type
      "isRefreshable": false // Whether the semantic model is refreshable.
    }
  ],
  "totalCount": 1,
  "nextLink": ""
}
