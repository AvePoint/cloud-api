# Set Archived Data Retention Period After Site Collection Restore

Use this API to set how long restored archived data of a site collection is retained before it is deleted from archive storage. This allows users to control how long the data remains available and helps to optimize storage usage after restoration.

Note the following:

- The retention period set by this API takes precedence over the one configured in Opus > **Storage Optimization** > **General settings**.

- This API is applied only once. If a job for deleting archived data after restoration has already started, this API will no longer have any effect. Subsequent jobs will instead follow the retention period configured in the Opus UI.

## Permission

The following permission is required to call this API.   
You must register an app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API | Permission |
|---|---|
| `/api/restore/SetRestoreGracePeriodSiteCollection` | records.readwrite.all |

## Request

This section provides the HTTP method and endpoint for setting how long restored archived data is retained before deletion from archive storage.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/api/restore/SetRestoreGracePeriodSiteCollection` | Sets the retention period for restored archived data before deletion from archive storage. |

## Request Parameters

The API requires a JSON request body.

| Parameter | Description | Type | Required? |
|---|---|---|---|
| scope | The URL of the target site collection. | string | Yes |
| deleteArchivedDataDaysAfterRestore | The number of days (0–365) to retain archived data in archive storage after restoration. | long | Yes |

## Response

The API response provides the operation result.

| Parameter | Description | Type |
|---|---|---|
| success | Indicates whether the request was processed successfully. | boolean |
| message | The result message. | string |

## Request Sample

To use this API, send a `POST` request to the specified endpoint, including necessary parameters as defined. The following request is an API call to the AvePoint Opus environment in the US - East region.

**URL**

```json
https://graph-us.avepointonlineservices.com/api/restore/SetRestoreGracePeriodSiteCollection
```

**Body (raw-JSON)**

```json
{
  "scope": "https://contoso.sharepoint.com/sites/Finance", // The URL of the target site collection
  "deleteArchivedDataDaysAfterRestore": 30 // The number of days to retain archived data in archive storage after restoration
}
```

## Response Sample

```json
{
  "success": true, // Indicates whether the request was processed successfully
  "message": null // The result message
}
```
