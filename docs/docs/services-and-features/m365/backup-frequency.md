# Backup Frequency

Get the backup frequency of all active services (`/backup/m365/settings/backup/frequency` navigation property) from Cloud Backup for Microsoft 365. By invoking the `/backup/m365/settings/backup/frequency` endpoint, users can get how often each service is backed up and when backup jobs are scheduled to run, helping you verify that your data protection policies are correctly applied.

## Permission

The following permission is required to call this API.  

You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|---|---|
|`/backup/m365/settings/backup/frequency` | microsoft365backup.settings.read.all|

## Request

This section outlines the HTTP method and endpoint used to retrieve the backup frequency. It provides a concise description of the action performed by the API call.  

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/backup/m365/settings/backup/frequency` | Gets the backup frequency of Cloud Backup for Microsoft 365. |

## Query Parameters

The API supports an optional query parameter to refine the location for Multi‑Geo tenants.

| Parameter | Description | Type | Required? |
| --- | --- | --- | --- |
| location | Available only for Multi-Geo tenants. If not specified, the backup frequency is retrieved from the central AOS location. For supported values, refer to [Parameter: location](./overview.md#parameter-location). | string | No |

## Responses

The API response provides the backup frequency for all active services. Each service in the response includes its daily backup frequency and the scheduled start times of backup jobs for the current day.

**Retrieved result:**

| Elements | Description | Type |
| --- | --- | --- |
| statusCode | Http Response Status Code | integer |
| message | Error message | string |
| errors | API error | ApiError |
| data | Backup frequency of all active services | Array of BackupFrequency |
| requestId | API request ID | string |
| timestamp | API request time | string |
| traceId | API trace ID | string |

**Backup frequency**

| Elements | Description | Type   |
| --- | --- | --- |
| serviceType | Service type. For valid values, refer to [Attribute: serviceType](./overview.md#attribute-servicetype). | integer |
| frequency  | Number of backup jobs scheduled to run within a single day | integer |
| backupStartTime | Collection of timestamps indicating when backup jobs are initiated or will be initiated on the current day (UTC) | Array of string |

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. This will return the backup frequency of active services in a structured format, enabling easy integration with other systems or applications.

The following request is an API call to the Cloud Backup for Microsoft 365 environment.  

```json
https://graph-us.avepointonlineservices.com/backup/m365/settings/backup/frequency
```

The following request is an API call to the Cloud Backup for Microsoft 365 environment for Multi-Geo tenant in the US - East region.

```json
https://graph-us.avepointonlineservices.com/backup/m365/settings/backup/frequency&Location=NAM
```

## Response Sample

If successful, this method returns a 200 OK response code and the backup frequency in the response body.

For details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "statusCode": 200, //Http Response Status Code
    "message": "", //Error message
    "data": [
        {
            "serviceType": 0, // Service type
            "frequency": 4, // Number of backup jobs scheduled to run within a single day
            "backupStartTime": [
                "2026-02-27T03:54:22Z", // UTC timestamp for the start time of a backup job initiated or will initiate on the current day.
                "2026-02-27T09:54:22Z",
                "2026-02-27T15:54:22Z",
                "2026-02-27T21:54:22Z"
            ]
        },
        {
            "serviceType": 1,
            "frequency": 1,
            "backupStartTime": [
                "2026-02-27T03:54:22Z"
            ]
        },
        {
            "serviceType": 2,
            "frequency": 1,
            "backupStartTime": [
                "2026-02-27T03:54:22Z"
            ]
        }
    ],
    "requestId": "0HNEVHLNSPSEJ:00000004", //API request ID
    "timestamp": "2025-08-20T03:45:46.3561083Z",  //API request time
    "traceId": "00-670aa1d01485c1a7bbcc88bd48b05ed7-ecfba726763bda2a-00" //API trace ID
}
```
