
# Retrieve Import Users Status

Use this API to query the status of a user import task (`/admin/shareSetting/import-users/{id}` navigation property). This article outlines the necessary permissions, available methods, and models used for interacting with the API.

---

## Permission
The following permission is required to call this API.

You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API | Permission |
|-----|------------|
| `/admin/shareSetting/import-users/{id}` | confide.graph.readwrite.all |



## Request
This section outlines the HTTP method and endpoint used to retrieve import users status. It provides a concise description of the action performed by the API call.

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/admin/shareSetting/import-users/{id}` | Retrieves import users task status. |

## Query Parameters
The API supports the following query parameter to specify the import task for which you want to view status.

| Parameter | Description | Type | Required? |
|-----------|-------------|------|----------|
| id | The unique identifier (UUID) of the import users task. | string | Yes |

## Response

The API response provides detailed information about the import users status.

| Code | Description | Schema |
|------|-------------|--------|
| 200  | OK, the request was successful and the method returns the task status | [ImportUserStatusResponse Properties](#importuserstatusresponse-properties) |
| 400  | Bad Request | [ErrorResponse](#errorresponse) |
| 401  | Unauthorized |  [ErrorResponse](#errorresponse) |
| 500  | Internal Server Error |  [ErrorResponse](#errorresponse) |

### Response Models
The following sections describe the response models to retrieve import user status.

#### ImportUserStatusResponse Properties

| Property           | Type    | Description |
|--------------------|---------|-------------|
| taskId           | string  | The unique identifier (UUID) of the import users task. |
| status         | string | The current status of the task. |
| totalCount     | integer | The total number of users in the import task. |
| processedCount  | integer | The number of users that have been processed. |
| failedCount      | integer | The number of users that failed to import. |
| items     | array of [ImportUserStatusItem Properties](#importuserstatusitem-properties) | An array of objects detailing the users who failed to import. |
| message          | string | A general message about the task status. |
| startTime          | string  | The time when the task started in ISO 8601 format. |
| finishTime        | string  | The time when the task finished in ISO 8601 format. |

#### ImportUserStatusItem Properties 

| Property         | Type    | Description |
|------------------|---------|-------------|
| email           | string  | The email address of the user. |
| success     | boolean  | Indicates if the user was imported. |
| status           | string | The import status of the user. |
| errorMessage          | string  | Any error message associated with the user's import failure. |


#### ErrorResponse

| Name | Type | Description |
|-------|------|-------------|
| traceId | string | The unique identifier used to trace and track the flow of a request. |
| error | string | The error message. |
| statusCode | [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code) | The HTTP error code. |



## Request Example

```json
https://graph-us.avepointonlineservices.com/confide/admin/shareSetting/import-users/a3f1c2e4-****-4e2a-****-2c3d****6a7b 
```

## Response Sample

If successful, this method returns a 200 OK response code and the import task status in the response body.


```json
{
    "data": {
            "taskId": "a3f1c2e4-****-4e2a-****-2c3d****6a7b", // The unique identifier of the import task.
            "status": "Completed", // The current status of the task.
            "totalCount": 2, // The total number of users in the import task.
            "processedCount": 2, // The number of users that have been processed.
            "failedCount": 1, // The number of users that failed to import.
            "items": [ 
                {
                    "email": "user1@example.com", // The email address of the user.
                    "success": false, // Indicates if the user was imported.
                    "status": "Failed", // The import status of the user.
                    "errorMessage": null // Any error message associated with the user's import failure.
                },
                {
                    "email": "user2@example.com", 
                    "success": false, 
                    "status": "Failed", 
                    "errorMessage": "Invalid email format." 
                }
            ],
            "message": "Import task finished.", // A general message about the task status.
            "startTime": "2025-12-03T10:00:00Z", // The time when the task started.
            "finishTime": "2025-12-03T10:01:00Z" // The time when the task finished.
    }
}
```


