# Retrieve App Launches

Use this API to access and retrieve information of your Power App launches.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/powerapps/{appId}/launches` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve information of the launches of your apps.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerapps/{appId}/launches` | Retrieves your apps launches | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
|appId | The unique identifier of the app whose launches will be retrieved. | string | Yes |
|fromDate | The date after which the launches will be retrieved. By default, the start date and time is "1/1/0001 12:00:00". | datetime | No |
|toDate | The date before which the launches will be retrieved. By default, the end date and time is "12/31/9999 23:59:59". | datetime | No |
| top | The number of activity records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of the launches are retrieved. By default, data of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the apps' launches retrieved. Each record in the response includes various attributes that describe its properties and status.

| Elements      | Description                                                  | Type   |
|---------------|--------------------------------------------------------------|--------|
| id            | The unique identifier for the app launch.                   | string |
| objectId      | The unique identifier of the app related to the app launch. | string |
| creationTime  | The date and time when the launch started.                  | string |
| userId        | The UPN (User Principal Name) of the user who launched the app. | string |
| userKey       | An alternative ID for the user identified in the UserId property. | string |
| userType      | The type of user who performed the operation.                | string |
| clientIP      | The IP address of the client device from which the app was launched. | string |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/powerapps/8A40E648-FD97-4FBA-****-66AD1A8BE89A/launches
```
## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "launches": [
    {
      "id": "", // The unique identifier for the app launch
      "objectId": "", // The unique identifier of the app related to the launch
      "creationTime": "", // The date and time when the app was launched
      "userId": "", // The UPN (User Principal Name) of the user who launched the app
      "userKey": "", // An alternative ID for the user identified in the UserId property
      "userType": "", // The type of user who performed the operation
      "clientIP": "", //The IP address of the client device from which the app was launched
    }
  ],
  "totalCount": 1,
  "nextLink": ""
}
