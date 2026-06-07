# Execute Restore Job

Perform a restore job (`/backup/m365/restore/jobs` navigation property) in Cloud Backup for Microsoft 365. By invoking the `/backup/m365/restore/jobs` endpoint, users can submit a granular restore request for supported Microsoft 365 workloads and receive the generated restore job ID for follow-up tracking.

> [!NOTE]
> This API currently supports restoring files and folders in site collections and OneDrive only.

## Permission

The following permission is required to call this API.

You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
| `/backup/m365/restore/jobs` | microsoft365backup.restore.readwrite.all |

## Request

This section outlines the HTTP method and endpoint used to perform a restore job. It provides a concise description of the action performed by the API call.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST   | `/backup/m365/restore/jobs` | Performs a restore job in Cloud Backup for Microsoft 365. |

## Query Parameters

The API supports an optional query parameter to refine the location for Multi‑Geo tenants.

| Parameter | Description | Type | Required? |
| --- | --- | --- | --- |
| location  | Available only for Multi-Geo tenants. If not specified, the restore job uses data from the central AOS location. For supported values, refer to [Parameter: location](../overview.md#parameter-location). | string | No |

## Body Parameters

The API supports several body parameters to define the restore scope, target, and recovery point.

> [!NOTE]
> For OneDrive requests, the restore scope is determined by `oneDriveRestoreScope.oneDriveUpn`. For other supported services, the restore scope is determined by `siteRestoreScope.siteUrl`. If both scope objects are provided, the API uses the one that matches `serviceType`.

| Parameter | Description | Type | Required? |
| --- | --- | --- | --- |
| serviceType | Sets the Microsoft 365 service to restore. Valid values: <br><ul><li>**1** for SharePoint Online</li><li>**2** for OneDrive</li><li>**3** for Microsoft 365 Groups</li><li>**6** for Teams</li></ul> | integer | Yes |
| recoveryDateTime | Sets the upper bound of the recovery point (UTC). The restore uses the latest available backup before this timestamp. Must be in ISO 8601 UTC format: `yyyy-MM-ddTHH:mm:ssZ` or `yyyy-MM-ddTHH:mm:ss.fffffffZ`. Example: `2026-02-27T03:54:22Z`. | string | Yes |
| siteRestoreScope | Defines the restore scope and targets for site-based services. Required when `serviceType` is **1**, **3**, or **6**. | SiteRestoreScope | Conditional |
| oneDriveRestoreScope | Defines the restore scope and targets for OneDrive. required when `serviceType` is 2. | OneDriveRestoreScope | Conditional |

**siteRestoreScope:**

| Parameter | Description | Type |
| --- | --- | --- |
| siteUrl | The site or subsite URL used to locate the backup content. Examples: `https://test.sharepoint.com/sites/Finance` (site collection URL); `https://test.sharepoint.com/sites/Finance/APAC` (subsite URL). | string |
| restoreTargets | A list of restore target groups. Across all `restoreTargets`, the total number of file and folder paths cannot exceed 20. Parent and child paths cannot be included in the same request. | Array of RestoreTarget |

**oneDriveRestoreScope:**

| Parameter | Description | Type |
| --- | --- | --- | 
| oneDriveUpn | The user principal name of the OneDrive account to restore. | string |
| restoreTargets | A list of restore target groups. Across all `restoreTargets`, the total number of file and folder paths cannot exceed 20. Parent and child paths cannot be included in the same request. | Array of RestoreTarget |

**restoreTargets**

| Parameter | Description | Type |
| --- | --- | --- |
| libraryName | The name of the library that contains the items to restore. | string |
| files | The files to restore from the library. Can be provided together with `folders`, but at least one must be specified. | Array of RestoreTargetPath |
| folders | The folders to restore from the library. Can be provided together with `files`, but at least one must be specified. | Array of RestoreTargetPath |

**files/folders:**

| Parameter | Description | Type |
| --- | --- | --- |
| relativePath | The relative path of the file or folder within the library. Empty values are not allowed. | string |

## Responses

The API returns the restore job ID upon success. If the request is invalid, field-level validation errors are returned in the `errors` collection. If too many restore or export jobs are running, the API returns 429 Too Many Requests.

**Retrieved result:**

| Elements   | Description                     | Type              |
| ---------- | ------------------------------- | ----------------- |
| statusCode | Http Response Status Code       | integer           |
| message    | Error message                   | string            |
| errors     | API error                       | Array of ApiError |
| data       | Created restore job information | Restore result    |
| requestId  | API request ID                  | string            |
| timestamp  | API request time                | string            |
| traceId    | API trace ID                    | string            |

**Created restore job information**

| Elements | Description                   | Type   |
| -------- | ----------------------------- | ------ |
| jobId    | Generated restore job ID      | string |

**API error:**

| Elements | Description                           | Type   |
| -------- | --------------------------------------| ------ |
| code     | Error code for the failed validation  | string |
| field    | Request field that failed validation  | string |
| message  | Validation error message.             | string |

## Request Sample

To use this API, send a `POST` request to the specified endpoint with a JSON request body. This creates a restore job and returns the job ID that can be used for later tracking.

The following request is an API call to the Cloud Backup for Microsoft 365 environment in the US - East region.

**URL**

```json
https://graph-us.avepointonlineservices.com/backup/m365/restore/jobs?Location=NAM
```

**Body - SharePoint Online Example (raw-JSON)**

```json
{
  "serviceType": 1, // The Microsoft 365 service to restore.
  "recoveryDateTime": "2026-02-27T03:54:22Z", // The upper bound of the recovery point in UTC.
  "siteRestoreScope": {
    "siteUrl": "https://contoso.sharepoint.com/sites/Finance", // The site URL used to locate the backup content.
    "restoreTargets": [
      {
        "libraryName": "Documents", // The name of the library that contains the items to restore.
        "folders": [
          {
            "relativePath": "Shared/Reports/2026" // The relative path of the folder within the library.
          }
        ],
        "files": [
          {
            "relativePath": "Shared/Budget.xlsx" //The relative path of the file within the library.
          }
        ]
      }
    ]
  }
}
```

**Body - OneDrive Example (raw-JSON)**

```json
{
  "serviceType": 2, // The Microsoft 365 service to restore.
  "recoveryDateTime": "2026-02-27T03:54:22Z", // The upper bound of the recovery point in UTC.
  "oneDriveRestoreScope": {
    "oneDriveUpn": "alexw@contoso.onmicrosoft.com", // The user principal name of the OneDrive account to restore.
    "restoreTargets": [
      {
        "libraryName": "Documents", // The name of the library that contains the items to restore.
        "folders": [
          {
            "relativePath": "Shared/Reports/2026" ////The relative path of the folder within the library.
          }
          }
        ]
      }
    ]
  }
}
```

## Response Sample

If successful, this method returns a 200 OK response code and the created restore job information in the response body.

For details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "statusCode": 200, //Http Response Status Code
  "message": "", //Error message
  "data": {
    "jobId": "RS202602270354220001" //Generated restore job ID
  },
  "requestId": "0HNEVHLNSPSEJ:00000008", //API request ID
  "timestamp": "2026-02-27T03:54:23.1052191Z", //API request time
  "traceId": "00-670aa1d01485c1a7bbcc88bd48b05ed7-ecfba726763bda2a-00" //API trace ID
}
```

If the request body is invalid, this method returns a 400 Bad Request response code.

```json
{
  "statusCode": 400, //Http Response Status Code
  "message": "Bad Request", //Error message
  "errors": [
    {
      "code": "InvalidParameter", // Error code for the failed validation
      "field": "SiteRestoreScope", // Request field that failed validation
      "message": "'Site Restore Scope' must not be empty." // Validation error message
    }
  ],
  "requestId": "0HNEVHLNSPSEJ:00000009", //API request ID
  "timestamp": "2026-02-27T03:55:10.8742191Z", //API request time
  "traceId": "00-8b1d1d01485c1a7bbcc88bd48b05ed7-ecfba726763bda2a-00" //API trace ID
}
```

If too many restore or export jobs are already running, this method returns a 429 Too Many Requests response code.

```json
{
  "statusCode": 429, //Http Response Status Code
  "message": "There are already 3 restore/export jobs running, cannot start new restore job.", //Error message
  "requestId": "0HNEVHLNSPSEJ:00000010", //API request ID
  "timestamp": "2026-02-27T03:56:10.8742191Z", //API request time
  "traceId": "00-9b1d1d01485c1a7bbcc88bd48b05ed7-ecfba726763bda2a-00" //API trace ID
}
```
