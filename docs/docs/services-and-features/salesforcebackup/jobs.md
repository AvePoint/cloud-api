# Retrieve Job Information

Get the job-related information (`/backup/sfbapi/jobs` navigation property) from Cloud Backup for Salesforce®. By invoking the `/backup/sfbapi/jobs` endpoint, users can  integrate Cloud Backup for Salesforce® via an API to monitor job statuses and events, enhancing the ability to manage, analyze, and optimize backup operations with precision and efficiency.  

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/backup/sfbapi/jobs` | salesforce.public.read.all |

## Request

This section outlines the HTTP method and endpoint used to retrieve job information. It provides a concise description of the action performed by the API call.  

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/backup/sfbapi/jobs` | Gets the job information of Cloud Backup for Salesforce®. |

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow uses to specify pagination, job types, time ranges, and other criteria to filter the results effectively.  

| Parameter | Description | Type | Required? |
| --- | --- | --- | --- |
| startTime | Sets a start time (UTC time) for the time range in ISO 8601 format. For example, 2024-01-01.| string | Yes |
| finishTime | Sets an end time (UTC time) for the time range in ISO 8601 format. For example, 2024-12-01.| string | Yes |
| type | Sets the job types that you want to get. <br> Valid values: <br> <ul><li> **0** for All <br> </li><li> **1** for Backup <br> </li><li> **2** for On-demand backup <br> </li><li> **3** for Restore <br> </li><li> **4** for Pre restore <br> </li><li> **5** for Compare</li><li> **6** for Archive</li><li> **7** for Simulation</li><li> **8** for Inactive data analysis</li><li> **9** for Retention</li><li> **10** for Discovery</li><li> **11** for Backup export</li><li> **12** for On-demand export</li><li> **13** for Auto export</li><li> **14** for Data cleanup</li><li> **15** for Sandbox seeding</li><li> **16** for Generate recovery point</li><li> **17** for Continuous data protection</li><li> **18** for Data service</li><li> **19** for On-demand data service</li><li> **20** for Audit log backup</li><li> **21** for Audit log export</li><li> **22** for Audit log auto export</li></ul>| enum | No |
| status | Sets the job status that you want to get. <br>  Valid values: <br> <ul><li> **0** for All <br> </li><li>**1** for In progress <br> </li><li>**2** for  Finished <br> </li><li>**3** for Finished with exception <br> </li><li>**4** for Failed <br> </li><li>**5** for Paused <br> </li><li>**6** for Stopped <br> </li><li>**7** for Skipped <br> </li></ul> | enum <br>  | No |
| level | Sets the level of the job run. <br> Valid values: <br> <ul><li>**0** for All <br> </li><li>**1** for Organization <br> </li><li>**2** for Object <br> </li><li>**3** for Record <br> </li><li>**4** for Field <br> </li><li>**5** for Metadata </li><li>**6** for N/A </li></ul>| enum | No |
| organizationId | Sets the source organization that you want to get. | string | No |
| pageIndex| Sets the starting number of the page to get the jobs. <br> The default value is 0.| enum | No |
| pageSize| Sets the number of jobs to display on one page. <br> The default value is 10. | integer | No |

## Responses

The API response provides detailed information about the jobs retrieved. Each job in the response includes various attributes that describe its properties and status.

**Retrieved result:**

| Elements | Description | Type |
| --- | --- | --- |
| statusCode | Http Response Status Code | integer |
| message | Error message | string |
| errors | API error | ApiError |
| data | A list of jobs | jobs |
| requestId | API Request ID | string |
| timestamp | API request time | string |
| traceId | API Trace ID | string |

**Job summary:**

| Elements | Description | Type |
| --- | --- | --- |
| totalCount | The total count of the retrieved jobs. | integer |
| nextLink | Reference to the next page of results. | string |
| jobs | The job details. | module |

**Job details:**

| Elements | Description | Type |
| --- | --- | --- |
| type | The type of the job. | enum |
| jobId | The unique identifier for the job. | string |
| startTime | The start time of the job in ISO 8601 format. | string |
| finishTime | The end time of the job in ISO 8601 format. | string |
| status | The status of the job. | enum |
| successfulRecords | Number of records successfully processed. | long |
| skippedRecords | Number of records skipped during processing. | long |
| failedRecords | Number of records with errors. | long |
| totalRecords | Total records involved in this job. | long |
| successfulMetadata | Number of metadata items successfully processed. | long |
| failedMetadata | Number of metadata items with errors. | long |
| totalMetadata | Total metadata items involved in the job. | long |
| successfulObjects | Number of objects successfully processed. | long |
| skippedObjects | Number of objects skipped during processing. | long |
| failedObjects | Number of objects with errors. | long |
| totalObjects | Total number of objects in this job. | long |
| dataSize | Total data size involved in this job (KB). | long |
| apiCalls | Total number of API calls involved in the job. | long |
| organizationId| Unique ID of the source organization involved in the job. | string |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant job details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the Cloud Backup for Salesforce® environment in the US - East region.  

```json
https://graph-us.avepointonlineservices.com/backup/sfbapi/jobs?startTime=2024-10-24&finishTime=2024-12-25&pageSize=10&pageIndex=1
```

## Response Sample

If successful, this method returns a 200 OK response code and a collection of jobs in the response body.  
For details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).  

```json
{
    "statusCode": 200, //Http Response Status Code
    "message": "", //Error message
    "data": {
        "totalCount":1, //The total count of the retrieved jobs
        "jobs": [
            {
                "type": 20, //The type of job
                "jobId": AI20241015105312327583, //Job ID
                "startTime": "2024-12-02T07:52:25Z", // The start time of the job in ISO 8601 format. UTC time.
                "finishTime": "2024-12-02T07:53:04Z", // The finished time of the job in ISO 8601 format. UTC time.
                "state": 2, // Job status Finished
                "successfulRecords": 0, // Number of successful records
                "skippedRecords": 0, // Number of skipped objects
                "failedRecords": 0, // Number of failed objects
                "totalRecords": 0, // Number of total records
                "successfulMetadata": 0, // Number of successful metadata
                "failedMetadata": 0, // Number of failed metadata
                "totalMetadata": 0, // Number of total metadata
                "successfulObjects": 2, // Number of successful objects
                "skippedObjects": 0, // Number of skipped objects
                "failedObjects": 0, // Number of failed objects
                "totalObjects": 2, // Number of total objects
            }
        ],
        "nextLink": "" // No left results  
     },
    "requestId": "0HNEVHLNSPSEJ:00000002", //API Request ID
    "timestamp": "2025-08-20T03:25:12.304891Z", //API request time
    "traceId": "00-f33571c212e19c7bad36b255e18b7df2-97d26a62bd4a5b70-00" //API Trace ID
}
