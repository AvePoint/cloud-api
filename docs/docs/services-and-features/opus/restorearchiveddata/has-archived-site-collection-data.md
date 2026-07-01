# Has Archived Site Collection Data

Use this API to check whether archived data exists for a site collection.

## Permission

The following permission is required to call this API.   
You must register an app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API | Permission |
|---|---|
| `/api/restore/HasArchivedSiteCollectionData` | records.readwrite.all |

## Request

This section outlines the HTTP method and endpoint used for checking whether archived data exists for a site collection.

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/api/restore/HasArchivedSiteCollectionData` | Checks whether archived data exists for a site collection. |

## Request Parameters

| Parameter | Description | Type | Required? |
|---|---|---|---|
| scope | The URL of the target site collection. | string | Yes |

## Response

The API response provides the archived data check result.

| Parameter | Description | Type |
|---|---|---|
| success | Indicates whether the request was processed successfully. | boolean |
| message | The result message. | string |
| hasArchivedData | Indicates whether archived data exists for a site collection. | boolean |
| scope | The URL of the target site collection. | string |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined. The following request is an API call to the AvePoint Opus environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/api/restore/HasArchivedSiteCollectionData?scope=https://contoso.sharepoint.com/sites/Finance
```

## Response Sample

```json
{
  "success": true, // Indicates whether the request was processed successfully
  "message": null, // The result message
  "hasArchivedData": true, // Indicates whether archived data exists for a site collection
  "scope": "https://contoso.sharepoint.com/sites/Finance" // The URL of the target site collection
}
```
