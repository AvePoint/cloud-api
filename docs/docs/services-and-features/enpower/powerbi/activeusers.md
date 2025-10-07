# Retrieve Power BI Active Users

Use this API to retrieve the Power BI active users.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/powerplatform/powerbi/powerbiactiveusers` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve the Power BI active users.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerbi/powerbiactiveusers` | Retrieves all your Power BI active users | 

## Query Parameters

The API supports the following query parameter to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| tenant | The tenant in which the users are retrieved. By default, data of all tenants are retrieved. | string | No |
|top| The number of users retrieved. | integer | No |

## Responses

The API response provides detailed information about the users retrieved. Each user in the response includes various attributes that describe its properties and status.

| Elements             | Description                                   | Type    |
|-----------------------|-----------------------------------------------|---------|
| userId                | The unique identifier of the user.                        | string  |
| userPrincipalName     | The user principal name.                   | string  |
| displayName           | The user display name.                          | string  |
| department            | The department of user.                            | string  |
| operation             | The operation of the audit record.                 | string  |
| activityTime          | The activity time of audit record.                 | string  |
| isSuccess             | Whether the operation succeeded.<br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br>| boolean |
| pbiObjectId           | The unique identifier of the Power BI object.              | string  |
| pbiObjectName         | The Power BI object name.                          | string  |
| pbiObjectType         | The Power BI object type.                          | string  |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/powerbi/powerbiactiveusers
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "powerBIActiveUsers": [
    {
      "userId": "cedd159a-620e-4a8c-****-7966c8beb45e", // The unique identifier of the user
      "userPrincipalName": "" //The user principal name      
      "displayName": "" // The user display name
      "department": "" // The department of user
      "operation": "CreateFolder" // The operation of the audit record
      "activityTime": "2025-08-13 02:01:32" // The activity time of audit record
      "isSuccess": true // Whether the operation succeeded
      "pbiObjectId": "de44dd0f-687c-4f8a-****-53edd31f7ac1" // The unique identifier of the Power BI object
      "pbiObjectName": "" // The Power BI object name
      "pbiObjectType": "Workspace" // The Power BI object type
    }
  ],
  "totalCount": 1,
  "nextLink": ""
}

