# Retrieve Semantic Model Counts by Data Source Types

Use this API to retrieve the semantic model count of each data source type.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/powerbi/semanticmodelcountbydatasourcetype` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve the semantic model counts.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerbi/semanticmodelcountbydatasourcetype` | Retrieves all your semantic model count by data source type | 

## Query Parameters

The API supports the following query parameter to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| tenant | The tenant in which data sources of artifacts are retrieved. By default, data of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the semantic model counts retrieved. Each semantic model count in the response includes various attributes that describe its properties and status.

| Elements           | Description                                                           | Type   | 
|--------------------|-----------------------------------------------------------------------|--------|
|datasourceType| The data source type. | string |
|count| The semantic model count of the type. | integer |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/powerbi/semanticmodelcountbydatasourcetype
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "semanticModelCounts": [
    {
      "datasourceType": "Extension", // The data source type
      "count": 1 // The semantic model count of the type
    }
  ],
  "totalCount": 1,
  "nextLink": ""
}

