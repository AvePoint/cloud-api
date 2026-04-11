# Update Confide Sharing Users

This API method (`/admin/shareSetting/update-users` navigation property) allows users to update permissions for privileged users in the Confide share center. This method is useful for managing user permissions in bulk.  


## Permission
The following permission is required to call this API.  

You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API | Permission required |
|-----|------------|
| `/admin/shareSetting/update-users` | confide.graph.readwrite.all |


## Request
This section outlines the HTTP method and endpoint used to update user permissions. It provides a concise description of the action performed by the API call.

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/admin/shareSetting/update-users` | Update privileged user permissions in the Confide share center. |

## Query Parameters

The API supports the following query parameters to define the users to be updated in Confide.

>[!Note] 
> The request body must be an array of `PrivilegedUser` objects.

### PrivilegedUser Properties

| Property                | Type    | Required | Description |
|-------------------------|---------|----------|-------------|
| email                   | string  | Yes      | The email address of the user. |
| isShareCoordinator      | boolean | No       | Can manage and share objects in the share center. |
| canConfigureScan        | boolean | No       | Can skip anti-virus scan for files greater than 2 GB. |
| canGenerateAccessCodeLinkInShareCenter      | boolean | No       | Can generate secure access links in the share center. |
| canShareLink            | boolean | No       | Can generate anonymous download links in a project. |
| canGenerateUploadLink   | boolean | No       | Can generate anonymous upload links in a project. |
| canGenerateDownloadLinkInShareCenter      | boolean | No       | Can generate anonymous download links in the share center. |
| canGenerateUploadLinkInShareCenter    | boolean | No       | Can generate anonymous upload links in the share center. |


## Response
The API response provides detailed information about the update users status.

| Code | Description | Schema |
|------|-------------|--------|
| 200  | OK, the request was successful and the method returns the task ID | [GUID Property](#guid-property) |
| 400  | Bad Request | [ErrorResponse](#errorresponse) |
| 401  | Unauthorized |  [ErrorResponse](#errorresponse) |
| 500  | Internal Server Error |  [ErrorResponse](#errorresponse) |


### GUID Property
If successful, the following GUID property is displayed in the response body.
| Name | Description | Type | 
|-------|------|-------------|
| taskId | The unique identifier (UUID) of the update users task. |string (uuid) | 

### ErrorResponse
If an error occurs, the following information is displayed in the response body.

| Name | Description | Type | 
|-------|------|-------------|
| traceId | The unique identifier used to trace and track the flow of a request. |string | 
| error | The error message. |string | 
| statusCode | The HTTP error code. |[HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code) | 


## Request Sample
To use this API, send a `POST` request to the specified endpoint.

```json
https://graph-us.avepointonlineservices.com/confide/admin/shareSetting/update-users

[
  {
    "email": "user1@example.com",
    "isShareCoordinator": true,
    "canShareLink": true
  },
  {
    "email": "user2@example.com",
    "isShareCoordinator": false,
    "canShareLink": true,
    "sendInvitationEmail": true
  }
  ...
]
```

## Response Sample

If successful, this method returns a 200 OK response code and the update task ID in the response body.

```json

{
    "data": {
        "taskId": "a3f1c2e4-****-4e2a-****-2c3d****6a7b" //The unique identifier (UUID) of the update users task
    }
}


```
