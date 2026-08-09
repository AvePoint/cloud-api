# Generate Site Metrics Report

Use this API to generate a site metrics report for multiple site collections of SharePoint Online and save it to a specified document library. The report includes metadata of documents and items from libraries and lists that contain a classification column. The report is exported as a SQLite database (.db) file, enabling integration with BI tools such as Power BI.

Before you call this API, verify the following prerequisites:

- Synchronization status: This report is generated from data stored in the Opus database. Ensure that all target site collections have already been synchronized to Opus.

- Destination library URL: Ensure that `DestinationLibraryUrl` is a valid URL that points to an existing document library.

## Permission

The following permission is required to call this API.   
You must register an app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API | Permission |
|---|---|
| `records/api/OpusReport/GenerateReport` | records.readwrite.all |

## Request

This section describes the HTTP method and endpoint used to generate a site metrics report and save it to a specified document library.

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `records/api/OpusReport/GenerateReport` | Generates a site metrics report and saves it to a specified document library. |

## Request Parameters

Provide the following parameters in the request body when you submit a request to generate a site metrics report.

| Parameter | Description | Type | Required? |
|-----------|-------------|------|-----------|
| `SiteCollectionUrls` | A list of SharePoint Online site collection URLs whose data you want to export. | `List<string>` | Yes |
| `DestinationLibraryUrl` | The URL of the target SharePoint Online document library where the exported report will be saved. | `string` | Yes |

## Response

The response returns the result of the request.

| Parameter | Description | Type | Required? |
|-----------|-------------|------|-----------|
| `Success` | Indicates whether the request was processed successfully. | `bool` | Yes |
| `Message` | Provides additional information about the result, such as a success confirmation or error details. | `string` | Yes |

## Request Sample

Send a `POST` request to the endpoint with the required parameters. The following example uses the AvePoint Opus environment in the US - East region.

**URL**

```json
https://graph-us.avepointonlineservices.com/records/api/OpusReport/GenerateReport
```
**Body (raw-JSON)**

```json
{
  "SiteCollectionUrls": [ // A list of SharePoint Online site collection URLs whose data you want to export
    "https://contoso.sharepoint.com/sites/site1",
    "https://contoso.sharepoint.com/sites/site2"
  ],
  "DestinationLibraryUrl": "https://contoso.sharepoint.com/sites/reporting/Shared%20Documents" // The URL of the target SharePoint Online document library where the exported report will be saved
}
```

## Response Sample

**Successful Response Sample**

```json
{
  "Success": true,
  "Message": "Report export job has been submitted successfully."
}
```

**Error Response Sample**

```json
{
  "Success": false,
  "Message": "The destination library URL is invalid."
}
```