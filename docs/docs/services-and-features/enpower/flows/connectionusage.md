# Retrieve Connection Usage of Cloud Flows

Use this API to access and retrieve information of your Power Automate cloud flows' connection usage.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/connectionusage/cloudflows` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve information of the connection usage of your cloud flows.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/connectionusage/cloudflows` | Retrieves your cloud flows' connection usage | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
|flowId | The unique identifier of the flow whose connection usage will be retrieved. | string | Yes |
| top | The number of connection usage records records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of the connection usage is retrieved. By default, data of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the cloud flows' connection usage retrieved. Each record in the response includes various attributes that describe its properties and status.

| Elements        | Description                                                  | Type   |
|-----------------|--------------------------------------------------------------|--------|
| flowId          | The unique identifier for the cloud flow. By default, connection usage of all cloud flows are retrieved.                  | string |
| environmentId    | The unique identifier of the environment that the flow belongs to. | string |
| connectionId    | The unique identifier of the connection used by the flow.   | string |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/connectionusage/cloudflows
```
## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "connectionUsageCloudFlows": [
    {
      "flowId": "", // The unique identifier for the cloud flow
      "environmentId": "", // The unique identifier of the environment that the flow belongs to
      "connectionId": "", // The unique identifier of the connection used by the flow
    }
  ],
  "totalCount": 1,
  "nextLink": ""
}
