# Retrieve Scan Job Information

Use this API to access and retrieve information of your scan jobs.

## Permission

The following permission is required to call the API. You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API         | Permission                  |
| ----------- | --------------------------- |
| `/aos/jobs` | autodiscovery.readwrite.all |

## Request

This section outlines the HTTP method and endpoint that is used to retrieve scan jobs.

| Method | Endpoint  | Description                         |
| ------ | --------- | ----------------------------------- |
| GET    | /aos/jobs | Retrieves your scan job information |

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description                                                  | Type    | Required |
| ---------- | ------------------------------------------------------------ | ------- | -------- |
| top        | The number of jobs retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No       |
| skip       | Requests the number of items in the queried collection that are to be skipped and not included in the result. | integer | No       |
| orderby    | The order in which items are returned. By default, order by start time of the jobs. Default order by column is StartTime. | string  | No       |
| sortorder  | Specifies a custom sort order for results<br />Valid values: <br><br />0: (ASC)<br/><br />1: (DESC)<br/> | integer | No       |
| search     | Search jobs(just support Job Id)                             | string  | No       |

## Response

The API response provides detailed information about the scan jobs retrieved.

| Code | Description                                                  |
| ---- | ------------------------------------------------------------ |
| 200  | OK – The request was successful, and the response contains the requested data. |
| 400  | Bad Request – If an error occurs, the method returns this code. |

## Response Models

The following sections describe the response models to get scan jobs.

| Name       | Description                                                  | Type    |
| ---------- | ------------------------------------------------------------ | ------- |
| jobs       | A list containing jobs with detailed information. For the detailed list of responses, refer to Scan Job Detail | list    |
| totalCount | Total number of jobs retrieved.                              | integer |
| nextLink   | Reference to the next page of results                        | string  |

## Scan Job Detail

| Elements        | Description                                                  | Type   |
| --------------- | ------------------------------------------------------------ | ------ |
| id              | The unique identifier for the scan job.                      | string |
| type            | The job type of the scan job<br />0: Microsoft 365 or Power Platform scan job<br />10: Google scan job<br />11: Batch import job | enum   |
| state           | The status of the scan job.<br />0: None<br />1: Running<br />2: Finished<br />3: Failed<br />4: Finished with Exception<br />5: Skipped<br />10: Stopped | enum   |
| startTime       | The start time of the scan job.                              | string |
| finishTime      | The end time of the scan job                                 | string |
| scanProfileName | The scan profile name for the scan job                       | string |
| category        | The scan profile category for the scan job<br />0: Microsoft 365 Scan Profile<br />1: Power Platform Scan Profile<br />2: Active Directory Scan Profile<br />3: Google Scan Profile | enum   |
| extension       | Current the value is null which used to extension later      | Object |

## Request Sample

The following request is an API call to the AvePoint Online Services (AOS) test environment. The API method being used is ***/aos/jobs***. 

```tex
https://graph-us.avepointonlineservices.com/aos/jobs?top=2&orderby=StartTime&sortorder=1
```

## Response Sample

If successful, this method returns a 200 OK response code and a collection of jobs in the response body.

```json
{
    "jobs": [
        {
            "id": "Scan20240926055840723067",
            "type": 0,
            "state": 2,
            "startTime": "2024-09-26T05:58:40.4092427+00:00",
            "finishTime": "2024-09-26T05:59:12.2300688+00:00",       
            "scanProfileName": "scan sharepoint sites",
            "category": 0,
            "extension": null
        },
        {
            "id": "Scan20240926051311702920",
            "type": 0,
            "state": 2,
            "startTime": "2024-09-26T05:13:11.0634642+00:00",
            "finishTime": "2024-09-26T05:13:42.3793844+00:00",
            "scanProfileName": "scan power platform",
            "category": 0,
            "extension": null
        }
    ],
    "nextLink": "https://graph-us.avepointonlineservices.com/aos/jobs?orderby=StartTime&sortorder=1&top=2&skip=1",
    "totalCount": 2
}
```

