# Retrieve Scan Job Information

Get the scan job information (`/aos/jobs` navigation property) from AvePoint Online Services.

## Permission

The following permission is required to call the API. You must register an app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API         | Permission                  |
| ----------- | --------------------------- |
| `/aos/jobs` | autodiscovery.readwrite.all |

## Request

This section outlines the HTTP method and endpoint that is used to retrieve scan jobs.

| Method | Endpoint  | Description                         |
| ------ | --------- | ----------------------------------- |
| GET    | `/aos/jobs` | Gets the scan job information of AvePoint Online Services. |

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameter | Description                                                  | Type    | Required |
| ---------- | ------------------------------------------------------------ | ------- | -------- |
| top        | Sets the number of jobs to display on one page. The default value is 100. You can enter a number from 1 to 1000. | integer | No       |
| skip       | Specifies the number of items to skip in the queried collection before retrieving the results. The default value is 0.| integer | No       |
| orderby    | Sets the order in which items are returned. By default, the returned items are ordered by jobs' startTime values. | string  | No       |
| sortorder  | Sets a custom order (sort by time) for returned items in the results.<br> Valid values:<br> <ul><li> **0** (oldest on top)</li><li> **1** (newest on top) </li></ul> | integer | No       |
| search     | Specifies Job ID values to search jobs.                             | string  | No       |

## Response

The API response provides detailed information about the jobs retrieved. Each job in the response includes various attributes that describe its properties and status.

| Name       | Description                                                  | Type    |
| ---------- | ------------------------------------------------------------ | ------- |
| jobs       | A list containing jobs with detailed information. | list    |
| totalCount | Total number of retrieved jobs.                              | integer |
| nextLink   | Reference to the next page of results.                        | string  |

**Job details**

Each job retrieved through the API includes detailed attributes that offer insights into its execution and outcome. These attributes assist in evaluating the performance, status, and specifics of each job, facilitating effective management and analysis.

| Elements        | Description                                                  | Type   |
| --------------- | ------------------------------------------------------------ | ------ |
| id              | Unique identifier for the scan job.                      | string |
| type            | Type of the scan job. <br> Valid values:<br> <ul><li> **0** (scan job for Microsoft 365 or Power Platform objects)</li><li> **10** (scan job for Google objects) </li><li> **11** (batch import job) </li></ul> | enum   |
| state           | Status of the scan job.<br> Valid values:<br> <ul><li> **1** for Running </li><li> **2** for Finished </li><li>**3** for Failed</li><li>**4** for Finished with exception</li><li>**5** for Skipped</li><li>**10** for Stopped</li></ul> | enum   |
| startTime       | The start time of the job in ISO 8601 format.                              | string |
| finishTime      | The end time of the job in ISO 8601 format.                                 | string |
| scanProfileName | The name of the scan profile used to run the scan job.                       | string |
| category        | The scan profile category for the scan job.<br> Valid values:<br> <ul><li> **0** (Microsoft 365) </li><li> **1** (Power Platform) </li><li> **2** (Active Directory) </li><li> **3** (Google) </li></ul> | enum   |
| extension       | This parameter is for adding extension later. The current value is **null**.     | Object |

## Request Sample

The following request structure is designed to query a collection of jobs with flexible parameters, allowing you to refine your search based on various criteria. This request supports pagination and filtering to efficiently manage and retrieve job data. This request sample is an API call to the AvePoint Online Services environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/aos/jobs?top=2&orderby=StartTime&sortorder=1

```

## Response Sample

If successful, this method returns a 200 OK response code and a collection of jobs in the response body. For details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "jobs": [
        {
            "id": "Scan20240926055840723067", // A scan job ID
            "type": 0, // Type of the job is to scan Microsoft 365 or Power Platform objects
            "state": 2, // Status of the job is Finished
            "startTime": "2024-09-26T05:58:40.4092427+00:00", // UTC timestamp for the start time of the job
            "finishTime": "2024-09-26T05:59:12.2300688+00:00", // UTC timestamp for the finished time of the job       
            "scanProfileName": "scan sharepoint sites", // The name of the scan profile used to run the scan job
            "category": 0, // The scan profile category is Microsoft 365
            "extension": null, // No extension
        },
        {
            "id": "Scan20240926051311702920", // A scan job ID
            "type": 0, // Type of the job is to scan Microsoft 365 or Power Platform objects 
            "state": 2, // Status of the job is Finished
            "startTime": "2024-09-26T05:13:11.0634642+00:00", // UTC timestamp for the start time of the job
            "finishTime": "2024-09-26T05:13:42.3793844+00:00", // UTC timestamp for the finished time of the job
            "scanProfileName": "scan power platform", // The name of the scan profile used to run the scan job
            "category": 0, // The scan profile category is Microsoft 365
            "extension": null, // No extension
        }
    ],
    "nextLink": "https://graph-us.avepointonlineservices.com/aos/jobs?orderby=StartTime&sortorder=1&top=2&skip=1", // Link to the next page of results
    "totalCount": 2, // The total number of retrieved jobs
}
```

