# Restore Site Collection

Use this API to start a job for restoring the archived data of a site collection.

## Permission

The following permission is required to call this API.   
You must register an app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API | Permission |
|---|---|
| `/api/restore/RestoreSiteCollection` | records.readwrite.all |

## Request

This section outlines the HTTP method and endpoint used to start a job for restoring the archived data of a site collection.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/api/restore/RestoreSiteCollection` | Starts a job for restoring the archived data of a site collection. |

## Request Parameters

The API requires a JSON request body.

| Parameter | Description | Type | Required? |
|---|---|---|---|
| scope | The URL of the target site collection. | string | Yes |
| conflictResolution | The conflict resolution for primary content.<ul><li> **0** - Overwrite</li><li>**1** - Skip</li><li> **2** - Append</li></ul> | integer | No |
| appsConflictResolution | The conflict resolution for apps data.<ul><li> **0** - Overwrite</li><li>**1** - Skip</li><li> **2** - Append</li></ul> | integer | No |
| includeWorkflowDefinition | Indicates whether to include workflow definitions in the restore operation. | boolean | No |
| includeSharingLink | Indicates whether to include sharing links in the restore operation. | boolean | No |
| siteAdministratorUserPrincipalName | The User Principal Name (UPN) of the Microsoft 365 account to assign to the Site admins group of the site collection being restored. | string | No |

## Response

The API response provides the restore execution result.

| Parameter | Description | Type |
|---|---|---|
| success | Indicates whether the request was processed successfully. | boolean |
| message | The result message. | string |
| jobId | The ID of the restore job. You can use this job ID for tracking job status and progress. | string |

## Request Sample

To use this API, send a `POST` request to the specified endpoint, including necessary parameters as defined. The following request is an API call to the AvePoint Opus environment in the US - East region. 

**URL**
```json
https://graph-us.avepointonlineservices.com/api/restore/RestoreSiteCollection
```
**Body (raw-JSON)**

```json
{
  "scope": "https://contoso.sharepoint.com/sites/Finance", // The URL of the target site collection
  "conflictResolution": 1, // The conflict resolution for primary content
  "appsConflictResolution": 1, // The conflict resolution for apps data
  "includeWorkflowDefinition": false, // Indicates whether to include workflow definitions in the restore operation
  "includeSharingLink": false, // Indicates whether to include sharing links in the restore operation
  "siteAdministratorUserPrincipalName": "admin@contoso.com", // The User Principal Name (UPN) of the Microsoft 365 account to assign to the Site admins group of the site collection being restored
}
```

## Response Sample

```json
{
  "success": true, // Indicates whether the request was processed successfully
  "message": null, // The result message
  "jobId": "8f1678a9-****-****-****-745212ef3c2a" // The ID of the restore job
}
```
