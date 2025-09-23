# Retrieve Cloud Flow Running History

Use this API to access and retrieve information of your Power Automate cloud flows' running history.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/powerautomate/cloudflows/{flowId}/runs` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve information of the running history of your cloud flows.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerautomate/cloudflows/{flowId}/runs` | Retrieves your cloud flows' running history | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
|flowId | The unique identifier of the flow whose running history will be retrieved. | string | Yes |
|fromDate | The date after which the running history will be retrieved. By default, the start date and time is "1/1/0001 12:00:00". | datetime | No |
|toDate | The date before which the running history will be retrieved. By default, the end date and time is "12/31/9999 23:59:59". | datetime | No |
| top | The number of running history records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of the running history is retrieved. By default, data of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the cloud flows' running history retrieved. Each record in the response includes various attributes that describe its properties and status.

| Elements    | Description                                                  | Type   |
|-------------|--------------------------------------------------------------|--------|
| id          | The unique identifier for the flow run history record.      | string |
| objectId    | The unique identifier of the flow associated with this run history. | string |
| startTime   | The date and time when the flow run started.                | string |
| endTime     | The date and time when the flow run ended.                  | string |
| duration    | The total time taken for the flow run (endTime - startTime).| string |
| state       | The final status of the flow run.                            | string |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/powerautomate/cloudflows/8A40E648-FD97-4FBA-9B47-66AD1A8BE89A/runs
```
## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "runs": [
    {
      "id": "", // The unique identifier for the flow run history record
      "objectId": "", // The unique identifier of the flow related to the activity
      "creationTime": "", // The date and time when the activity was created
      "startTime": "", // The date and time when the flow run started
      "endTime": "", // The date and time when the flow run ended
      "duration": "", // The total time taken for the flow run (endTime - startTime)
      "state": "" // The final status of the flow run
    }
  ],
  "totalCount": 1,
  "nextLink": ""
}
