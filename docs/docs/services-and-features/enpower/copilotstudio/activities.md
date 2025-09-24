# Retrieve Agent Activities

Use this API to access and retrieve information of your Copilot Studio agents' activities.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/bot/{botId}/activities` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve information of the activities of your agents.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/bot/{botId}/activities` | Retrieves your agents' activities | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
|botId | The unique identifier of the agent whose activities will be retrieved. | string | Yes |
|fromDate | The date after which the activities will be retrieved. By default, the start date and time is "1/1/0001 12:00:00". | datetime | No |
|toDate | The date before which the activities will be retrieved. By default, the end date and time is "12/31/9999 23:59:59". | datetime | No |
| top | The number of activity records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of the activities are retrieved. By default, data of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the agents' activities retrieved. Each record in the response includes various attributes that describe its properties and status.

| Elements              | Description                                                  | Type   |
|-----------------------|--------------------------------------------------------------|--------|
| id                    | The unique identifier for the agent activity.               | string |
| objectId              | The unique identifier of the agent related to the activity. | string |
| creationTime          | The date and time when the activity was performed.          | string |
| userId                | The UPN (User Principal Name) of the user who performed the action. | string |
| userKey               | An alternative ID for the user identified in the UserId property. | string |
| userType              | The type of user who performed the operation.               | string |
| activityType          | The type of activity performed.                              | string |
| dataSource            | The data source names associated to the activity.           | string |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/bots/8A40E648-FD97-4FBA-9B47-66AD1A8BE89A/activities
```
## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "activities": [
    {
      "id": "", // The unique identifier for the agent activity
      "objectId": "", // The unique identifier of the agent related to the activity
      "creationTime": "", // The date and time when the activity was performed
      "userId": "", // The UPN (User Principal Name) of the user who performed the action
      "userKey": "", // An alternative ID for the user identified in the UserId property
      "userType": "", // The type of user who performed the operation
      "activityType": "", // The type of activity performed
      "dataSource": "" // The data source names associated to the activity
    }
  ],
  "totalCount": 1,
  "nextLink": ""
}