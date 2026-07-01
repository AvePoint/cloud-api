# Get Restore Job Status and Progress

Use this API to get the status and progress of a restore job.

## Permission

The following permission is required to call this API.   
You must register an app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API | Permission |
|---|---|
| `/api/restore/GetRestoreJobStatus` | records.readwrite.all |

## Request

This section outlines the HTTP method and endpoint used to get the status or progress of a restore job.

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/api/restore/GetRestoreJobStatus` | Gets the status and progress of a restore job. |

## Request Parameters

| Parameter | Description | Type | Required? |
|---|---|---|---|
| jobId | The ID of the restore job. | string | Yes |

## Response

The API response provides the restore job details.

| Parameter | Description | Type |
|---|---|---|
| success | Indicates whether the request was processed successfully. | boolean |
| message | The result message. | string |
| job | Job details. | object |

**Job Details**

| Parameter | Description | Type |
|---|---|---|
| id | The restore job ID. | string |
| status | The restore job status.<ul><li> **-1** - None</li><li>**0** - Waiting</li><li> **1** - In progress</li><li> **2** - Finished</li><li> **3** - Failed</li><li> **4** - Finished with exception</li><li> **5** - Stopped</li><li> **6** - Skipped</li><li> **7** - Stopping</li><li> **8** - Calculating</li><li> **9** - Pending</li><li> **10** - Timed out</li></ul> | integer |
| progress | The percentage of the restore job that has been completed. | integer |
| startTime | The restore job start time. | string |
| finishTime | The restore job finish time. | string |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined. The following request is an API call to the AvePoint Opus environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/api/restore/GetRestoreJobStatus?jobId=8f1678a9-****-****-****-745212ef3c2a
```

## Response Sample

```json
{
  "success": true, // Indicates whether the request was processed successfully
  "message": null, // The result message
  "job": {
    "id": "8f1678a9-****-****-****-745212ef3c2a", // The restore job ID
    "status": 2, // The restore job status
    "progress": 75, // The percentage of the restore job that has been completed
    "startTime": "2026-06-29T08:31:12Z", // The restore job start time
    "finishTime": null // The restore job finish time
  }
}
```
