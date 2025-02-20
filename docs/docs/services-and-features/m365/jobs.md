# Retrieve Job Information

Get the job-related information (`/backup/m365/cloudbackup/getjobs` navigation property) from Cloud Backup for Microsoft 365. By invoking the `/backup/m365/cloudbackup/getjobs` endpoint, users can gain comprehensive insights and granular access to job reports, enhancing the ability to manage, analyze, and optimize backup operations with precision and efficiency.  

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/backup/m365/cloudbackup/getjobs` | microsoft365backup.jobInfo.read.all | 


## Request

This section outlines the HTTP method and endpoint used to retrieve job information. It provides a concise description of the action performed by the API call.  

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/backup/m365/cloudbackup/getjobs` | Gets the job information of Cloud Backup for Microsoft 365. |

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow uses to specify pagination, job types, time ranges, and other criteria to filter the results effectively.  

[comment Please confirm the Required? info]: #

| Parameter | Description | Type | Required? |
| --- | --- | --- | --- |
| startTime | Sets a start time (UTC time) for the time range. For example, 2024-01-01.| string | No |
| finishTime | Sets an end time (UTC time) for the time range. For example, 2024-12-01.| string | No |
| jobType | Sets the job types that you want to get. <br> Valid values: <br> <ul><li> **0** for All <br> </li><li> **1** for Backup <br> </li><li> **2** for Restore <br> </li><li> **3** for Export <br> </li><li> **4** for Deletion <br> </li><li> **5** for Retention</li></ul>| enum | No |
| objectType | Sets the service type of the jobs to get. <br>  Valid values: <br> <ul><li> **0** for All <br> </li><li>**1** for Exchange Online <br> </li><li>**2** for  SharePoint Online <br> </li><li>**3** for OneDrive <br> </li><li>**4** for Microsoft 365 Groups <br> </li><li>**5** for Project Online <br> </li><li>**6** for Public Folder <br> </li><li>**7** for Teams <br> </li><li>**8** for Viva Engage <br> </li><li>**9** for Teams Chat <br> </li><li>**10** for Power BI <br> </li><li>**11** for Power Automate <br> </li><li>**12** for Power Apps</li></ul> | enum <br>  | No |
| jobState | Sets the job status. <br> Valid values: <br> <ul><li>**0** for All <br> </li><li>**1** for In Progress <br> </li><li>**2** for Finished <br> </li><li>**3** for Failed <br> </li><li>**4** for Finished with Exception <br> </li><li>**5** for Partially Finished </li></ul>|enum | No |
| pageIndex|	Sets the starting number of the page to get the jobs. <br> The default value is 0.| integer | No |
| pageSize|	Sets the number of jobs to display on one page. <br> The default value is 10. | integer | No |

## Responses

The API response provides detailed information about the jobs retrieved. Each job in the response includes various attributes that describe its properties and status.

**Retrieved result:**

| Elements | Description | Type |
| --- | --- | --- |
| totalNumber | The total count of the retrieved jobs | integer |
| jobs | A list of jobs | list |
| nextLink | Reference to the next page of results | string |

**Job summary:**

| Elements | Description | Type |
| --- | --- | --- |
| id | Job ID | string |
| state | Job status | string |
| startTime | Job started time | string |
| finishTime | Job finished time | string |
| duration | Duration in hours | string |
| backupDetails | Job details.  | module |
| jobErrors|A list of job errors| list|

**Backup details:**

| Elements | Description | Type |
| --- | --- | --- |
| totalNumber | Total count of objects | long |
| failedNumber | Number of objects with errors| long |
| successfulNumber | Number of successful objects | long |
| skippedNumber| Number of skipped objects | long |

**Job errors:**

| Elements | Description | Type |
| --- | --- | --- |
| isErrorCode | Whether this error has an error code associated. | boolean |
| value | error message | string |
| url | error code URL | string |
| number| Occurrences of the error in this job. | long |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant job details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the Cloud Backup for Microsoft 365 environment in the US - East region.  

```json
https://graph-us.avepointonlineservices.com/backup/m365/cloudbackup/getjobs?StartTime=2024-10-24&FinishTime=2024-12-25&ObjectType=0&PageSize=50&PageIndex=1
```

## Response Sample

If successful, this method returns a 200 OK response code and a collection of jobs in the response body.  
For details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).  

```json
{
    "totalCount": 2, //Total number of the retrieved jobs
    "jobs": [
        {
            "id": FB20241015105312327583, //Job ID
            "state": Finished, // Job status
            "startTime": "2024-12-02T07:52:25Z", // The start time of the job in ISO 8601 format. UTC time.
            "finishTime": "2024-12-02T07:53:04Z", // The finished time of the job in ISO 8601 format. UTC time.
            "duration": "0.011", // Job duration in hours
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
            "startTime": "2024-12-02T01:33:22Z", // UTC timestamp for the start time of the job
            "finishTime": "2024-12-02T01:34:10Z", // UTC timestamp for the finished time of the job
            "duration":  "0.014", // Job duration
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
