# Retrieve Power BI Data Source Details

Use this API to retrieve the details of all artifact data sources.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/powerbi/datasourcedetails` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve the data source details.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerbi/datasourcedetails` | Retrieves all your data source details | 

## Query Parameters

The API supports the following query parameter to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| tenant | The tenant in which data sources of artifacts are retrieved. By default, data of all tenants are retrieved. | string | No |
|top| The number of data source details retrieved. | integer | No |

## Responses

The API response provides detailed information about the artifacts data source retrieved. Each data source in the response includes various attributes that describe its properties and status.

| Elements           | Description                                                           | Type   | 
|--------------------|-----------------------------------------------------------------------|--------|
|datasourceId| The data source unique identifier. | string |
|datasourceType| Type of the data source. | string |
|connectionDetails| The connection details of the data source. | string |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/powerbi/datasourcedetails
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "datasourceDetails": [
    {
      "datasourceId": "b7b83ae1-a3be-4553-****-ba289d97cbdb", // Data source unique identifier
      "datasourceType": "Extension", // Data source type
      "connectionDetails": "{\"ExtensionDataSourceKind\":\"Goals\",\"ExtensionDataSourcePath\":\"Goals\"}", // Connection details
    }
  ],
  "totalCount": 1,
  "nextLink": ""
}

