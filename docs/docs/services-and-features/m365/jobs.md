# Retrieve Job Information

Get the job-related information (`/cloudbackup/jobs` navigation property) from Cloud Backup for Microsoft 365. By invoking the `/cloudbackup/jobs` endpoint, users can gain comprehensive insights and granular access to job reports, enhancing the ability to manage, analyze, and optimize backup operations with precision and efficiency.  

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](/docs/docs/Use%20AvePoint%20Graph%20Modern%20API.md/#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/cloudbackup/jobs` | microsoft365backup.jobInfo.read.all | 


## Request

This section outlines the HTTP method and endpoint used to retrieve job information. It provides a concise description of the action performed by the API call.  

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/cloudbackup/jobs` | Gets the job information of Cloud Backup for Microsoft 365. |

-------------------------

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow uses to specify pagination, job types, time ranges, and other criteria to filter the results effectively.  

| Elements | Description | Type | Required? |
| --- | --- | --- | --- |
| StartTime | Sets a start time (UTC time) for the time range. | long | Yes |
| FinishTime | Sets an end time (UTC time) for the time range.| long | Yes |
| JobType | Sets the job types that you want to get. <br> Valid values: <br> <ul><li> **0** for All <br> </li><li> **1** for Backup <br> </li><li> **2** for Restore <br> </li><li> **3** for Export <br> </li><li> **4** for Deletion <br> </li><li> **5** for Retention</li></ul>| Enum | Yes |
| ObjectType | Sets the service type of the jobs to get. <br>  Valid values: <br> <ul><li> **0** for All <br> </li><li>**1** for Exchange Online <br> </li><li>**2** for  SharePoint Online <br> </li><li>**3** for OneDrive <br> </li><li>**4** for Microsoft 365 Groups <br> </li><li>**5** for Project Online <br> </li><li>**6** for Public Folder <br> </li><li>**7** for Teams <br> </li><li>**8** for Viva Engage <br> </li><li>**9** for Teams Chat <br> </li><li>**10** for Power BI <br> </li><li>**11** for Power Automate <br> </li><li>**12** for Power Apps</li></ul> | Enum <br>  | Yes |
| JobState | Sets the job status. <br> Valid values: <br> <ul><li>**0** for All <br> </li><li>**1** for In Progress <br> </li><li>**2** for Finished <br> </li><li>**3** for Failed <br> </li><li>**4** for Finished with Exception <br> </li><li>**5** for Partially Finished </li></ul>|Enum | Yes |
| PageIndex|	Sets the starting number of the page to get the jobs. <br> The default value is 0.| int | Yes |
| PageSize|	Sets the number of jobs to display on one page. <br> The default value is 10. | int | Yes |

## Responses

The API response provides detailed information about the jobs retrieved. Each job in the response includes various attributes that describe its properties and status.

**Retrieved result:**

| Elements | Description | Type |
| --- | --- | --- |
| TotalCount | The total count of the retrieved jobs | int |
| Jobs | A list of jobs | List |
| NextLink | Reference to the next page of results | string |

**Job summary:**

| Elements | Description | Type |
| --- | --- | --- |
| Id | Job ID | string |
| State | Job status | string |
| StartTime | Job started time | long |
| FinishTime | Job finished time | long |
| Duration | Duration | long |
| BackupDetails | Job details | int |

**Backup details:**

| Elements | Description | Type |
| --- | --- | --- |
| TotalCount | Total count | long |
| FailedCount | Number of objects with errors| long |
| SuccessfulCount | Number of successful objects | long |
| SkippedCount| Number of skipped objects | long |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant job details in a structured format, enabling easy integration with other systems or applications.  

```json
https://graph-us.avepointonlineservices.com/cloudbackup/jobs?StartTime=0&FinishTime=0&ObjectType=0&PageSize=5&PageIndex=1
```

## Response Sample

If successful, this method returns a 200 OK response code and a collection of jobs in the response body.  
For details on the HTTP status code, refer to [HTTP Status Code](/docs/docs/Use%20AvePoint%20Graph%20Modern%20API.md/#http-status-code). 

```json
{
    "totalCount": 2, //Total number of the retrieved jobs
    "jobs": [
        {
            "id": FB20241015105312327583, //Job ID
            "state": Finished, // Job status
            "startTime": 638645575921780695, // UTC timestamp for the start time of the job
            "finishTime": 638645576438386696, // UTC timestamp for the finished time of the job
            "duration": 516606001, // Job duration
            "backupDetails": {
                "totalCount": 16, // Total number of objects involved
                "failedCount": 0, // Number of objects with errors
                "successfulCount": 14, // Number of successful objects
                "skippedCount": 2, // Number of skipped objects
            },
            "jobErrors": []
        },
        {
            "id": EFB20241015105312828443, //Job ID
            "state": Finished, // Job status
            "startTime": 638645575920763578, // UTC timestamp for the start time of the job
            "finishTime": 638645576482282882, // UTC timestamp for the finished time of the job
            "duration": 561519304, // Job duration
            "backupDetails": {
                "totalCount": 438, // Total number of objects involved
                "failedCount": 0, // Number of objects with errors
                "successfulCount": 438, // Number of successful objects
                "skippedCount": 0, // Number of skipped objects
            },
            "jobErrors": []
        }
    ],
    "nextLink": "" // no left results.
}
```
