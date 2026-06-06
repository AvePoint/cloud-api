# Retrieve Job Details

Get detailed information for a specific job (`/backup/m365/cloudbackupjobs/{jobId}` navigation property) from Cloud Backup for Microsoft 365. By invoking the `/backup/m365/cloudbackupjobs/{jobId}` endpoint, users can retrieve detailed job data, including status, execution timing, summary counts, and top errors, providing clear visibility into the performance and results of an individual job.

## Permission

The following permission is required to call this API.

You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
| `/backup/m365/cloudbackupjobs/{jobId}` | microsoft365backup.jobInfo.read.all |

## Request

This section outlines the HTTP method and endpoint used to retrieve a specific job. It provides a concise description of the action performed by the API call.

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/backup/m365/cloudbackupjobs/{jobId}` | Gets the information of a specific job in Cloud Backup for Microsoft 365. |

## Path Parameters

The API requires a path parameter to identify which job to retrieve.

| Parameter | Description | Type | Required? |
| --- | --- | --- | --- |
| jobId | The unique identifier of the job to retrieve. | string | Yes |

## Query Parameters

The API supports an optional query parameter to refine the location for Multi‑Geo tenants.

| Parameter | Description | Type | Required? |
| --- | --- | --- | --- |
| location  | Available only for Multi-Geo tenants. If not specified, the job information is retrieved from the central AOS location. For supported values, refer to [Parameter: location](../overview.md#parameter-location). | string | No |

## Responses

The API response provides the details of the requested job, including job status, execution timestamps, object counts, and top errors.

**Retrieved result:**

| Elements   | Description               | Type     |
| ---------- | ------------------------- | -------- |
| statusCode | Http Response Status Code | integer  |
| message    | Error message             | string   |
| errors     | API error                 | Array of ApiError |
| data       | Job information           | job      |
| requestId  | API Request ID            | string   |
| timestamp  | API request time          | string   |
| traceId    | API Trace ID              | string   |

**Job summary:**

| Elements      | Description          | Type                   |
| ------------- | -------------------- | ---------------------- |
| id            | Job ID               | string                 |
| state         | Job status           | string                 |
| startTime     | Job started time     | string                 |
| finishTime    | Job finished time    | string                 |
| duration      | Duration in hours    | string                 |
| backupDetails | Job details          | PublicApiBackupDetails |
| jobErrors     | A list of job errors | list                   |

**Job details:**

| Elements         | Description                   | Type |
| ---------------- | ----------------------------- | ---- |
| totalNumber      | Total count of objects        | long |
| failedNumber     | Number of objects with errors | long |
| successfulNumber | Number of successful objects  | long |
| skippedNumber    | Number of skipped objects     | long |

**Job errors:**

| Elements | Description | Type |
| --- | --- | --- |
| isErrorCode | Whether this error has an error code associated. | boolean |
| value | Error message | string |
| url | Error code URL | string |
| number | Occurrences of the error in this job | integer |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the detailed information of the requested job in a structured format. The following request is an API call to the Cloud Backup for Microsoft 365 environment for Multi-Geo tenant in the US - East region.

```json
https://graph-us.avepointonlineservices.com/backup/m365/cloudbackupjobs/IB20260423083407021666?Location=NAM
```

## Response Sample

If successful, this method returns a 200 OK response code and the requested job information in the response body.
For details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "statusCode": 200, //Http Response Status Code
  "message": "", //Error message
  "data": {
    "id": "FB20241015105312327583", //Job ID
    "state": "Finished", // Job status
    "startTime": "2024-12-02T07:52:25Z", // The start time of the job in ISO 8601 format. UTC time.
    "finishTime": "2024-12-02T07:53:04Z", // The finished time of the job in ISO 8601 format. UTC time.
    "duration": "0.011", // Job duration in hours
    "backupDetails": {
      "totalNumber": 16, // Total number of objects involved
      "failedNumber": 0, // Number of objects with errors
      "successfulNumber": 14, // Number of successful objects
      "skippedNumber": 2 // Number of skipped objects
    },
    "jobErrors": []
  },
  "requestId": "0HNEVHLNSPSEJ:00000010", //API Request ID
  "timestamp": "2026-04-22T07:25:12.304891Z", //API request time
  "traceId": "00-f33571c212e19c7bad36b255e18b7df2-97d26a62bd4a5b70-00" //API Trace ID
}
```
