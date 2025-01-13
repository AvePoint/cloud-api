# Retrieve Job Information

Get the job-related information (`backup/vm/jobs` navigation property) from Cloud Backup for IaaS + PaaS. By invoking the `backup/vm/jobs` endpoint, users can access detailed insights and data about specific job reports, enhancing the ability to manage and analyze job information efficiently.   

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `backup/vm/jobs` | PlatformBackup.ReadWrite.All |

## Request  

This section outlines the HTTP method and endpoint used to retrieve job information. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `backup/vm/jobs` | Retrieves comprehensive job information. |

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify time ranges, service types, and other criteria to filter the results effectively.

| Parameter |  Description | Type |Required | 
| ---- | ------------------- | -------- | ------ |
| searchText |  Searches by job ID or description. |string | No | 
| startTime | Sets a start time (UTC time) for the time range. format: ISO 8601 |string | No | 
| finishTime |  Sets an end time (UTC time) for the time range. format: ISO 8601 |string | No | 
| serviceType | Sets the service type of the jobs to get.<ul>  <li> **1** for Azure Virtual Machine</li>  <li> **2** for Microsoft Entra ID</li><li> **4** for Azure Storage</li>  <li> **64** for Admin Portal Settings</li><li> **128** for Common</li> <li> **256** for Amazon EC2</li> <li> **512** for Azure SQL</li><li> **1024** for Azure DevOps</li><li> **2048** for Azure SQL Database real backup</li><li> **4096** for Azure AD B2C</li></ul> | No | Enum |
| jobType |  Sets the job types that you want to get.<ul><li> **1** for Azure Virtual Machine Backup Job</li><li> **2** for Azure Virtual Machine Restore Job</li><li> **4** for Azure Virtual Machine File Level Export Job</li><li> **32** for Azure Virtual Machine Index Generation Job</li><li> **64** for Data Retention Job</li><li> **128** for Microsoft Entra ID Backup Job</li><li> **256** for Microsoft Entra ID Restore Job</li><li> **257** for Microsoft Entra ID Export Job</li><li> **1024** for Azure Storage Backup Job</li><li> **2048** for Azure Storage Restore Job</li><li> **4096** for Azure Storage Export Job</li><li> **20003** for Admin Portal Settings Backup Job</li><li> **20004** for Admin Portal Settings Export Job</li><li> **20006** for Admin Portal Settings Restore Job</li><li> **20009** for Amazon EC2 Backup Job</li><li> **20010** for Amazon EC2 Restore Job</li><li> **20012** for Azure SQL Backup Job</li><li> **20013** for Azure SQL Restore Job</li><li> **20014** for Azure DevOps Backup Job</li><li> **20015** for Azure DevOps Restore Job</li><li> **20016** for Azure SQL Backup Real Job</li><li> **20017** for Azure SQL Import Job</li><li> **20018** for Azure VM File Restore Job</li><li> **20019** for Azure AD B2C Backup Job</li><li> **20020** for Azure AD B2C Restore Job</li></ul> | No | Enum |
| pageNumber | Sets the starting number of the page. The default value is 0. | integer |No | 
| pageSize |  Sets the number of objects to display on one page. The default value is 10. |integer | No | 
| skiptoken |  Sets the skip token got from next link from previous request, if setting this one, PageNumber will be ignored. |  string |No |

## Response  

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.  

**Retrieved result:**

|Elements|Description | Type|
|---|---|---|
|totalCount|Total count of jobs matching the query parameters.|integer|
|jobs|A collection of jobs.|list|
|nextlink|Returns the link to the next page of results.|string|
|errorModel|Returns the request ID, date and the error code. See [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).|string|

**Job details:**
|Elements|Description | Type|
|---|---|---|
|jobId|Unique identifier for the job. |string|
|status|Indicates the state of the job.<ul>  <li>**0** for Not Started</li>  <li>**1** for In Progress</li>  <li>**2** for Successful</li>  <li>**4** for Skipped</li>  <li>**8** for Exception</li>  <li>**16** for Failed</li>  <li>**32** for Waiting</li>  <li>**64** for Stopped</li></ul> |enum|
|failedCount|Count of objects with errors.|integer|
|successfulCount|Count of objects successfully proceed.|integer|
|skippedCount|Count of objects skipped during processing.|integer|
|totalCount|Total count of objects in the job.|integer|
|startTime|The start time of the job. format: ISO 8601|string|
|finishTime|The end time of the job. format: ISO 8601|string|
|duration|Duration of the job.|string|
|comments|Comments for the job.|string|


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant job details in a structured format, enabling easy integration with other systems or applications.  

```json
https://graph-us.avepointonlineservices.com/backup/vm/jobs?serviceType=1&jobType=1&pageSize=5&startTime=2024-08-01T00:00:00Z&finishTime=2024-11-01T00:00:00Z
```

## Response Sample  

If successful, this method returns a 200 OK response code and a collection of  jobs in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](/docs/docs/Use%20AvePoint%20Graph%20Modern%20API.md/#http-status-code).

```json
{
    "totalCount": 51, // Total count of jobs
    "jobs": [
        {
            "jobId": "FB20241027081716326", // Unique job identifier 
            "status": 2, // Job status. 2 indicates the job is in progress.
            "failedCount": 0, // Count of objects with errors
            "successfulCount": 1, // Count of successful objects
            "skippedCount": 0, // Count of skipped objects
            "totalCount": 1, // Total count of objects
            "startTime": "2024-10-27T08:17:06Z", // Start time of the job
            "finishTime": "2024-10-27T08:21:08Z", // Finish time of the job
            "duration": "00:04:01", // Duration of the job
            "comments": "" // Comments for the job
        },
        {
            "jobId": "IB20241025160014096", // Unique job identifier
            "status": 2, // Job status. 2 indicates the job is in progress.
            "failedCount": 0, // Count of objects with errors
            "successfulCount": 10, // Count of successful objects
            "skippedCount": 35, // Count of skipped objects
            "totalCount": 45, // Total count of objects
            "startTime": "2024-10-25T16:00:14Z", // Start time of the job
            "finishTime": "2024-10-27T08:00:58Z", // Finish time of the job
            "duration": "1.16:00:44", // Duration of the job in days.hours:minutes:seconds format.
            "comments": "" // Comments for the job.
        },
        {
            "jobId": "IB20241010055858683", // Unique job identifier 
            "status": 2, // The job is in progress
            "failedCount": 0, // Count of objects with errors
            "successfulCount": 15, // Count of successful objects
            "skippedCount": 10, // Count of skipped objects
            "totalCount": 25, // Total count of objects
            "startTime": "2024-10-10T05:58:58Z", // Start time of the job
            "finishTime": "2024-10-10T06:59:13Z", // Finish time of the job
            "duration": "01:00:14", // Duration of the job in hours:minutes:seconds format.
            "comments": "" // Comments for the job
        },
        {
            "jobId": "IB20241002054145888", // Unique job identifier
            "status": 2, // The job is in progress
            "failedCount": 0, // Count of objects with errors
            "successfulCount": 15, // Count of successful objects
            "skippedCount": 20, // Count of skipped objects
            "totalCount": 35, // Total count of objects
            "startTime": "2024-10-02T05:41:45Z", // Start time of the job
            "finishTime": "2024-10-02T18:44:11Z", // Finish time of the job
            "duration": "13:02:26", // Duration of the job
            "comments": "" // Comments for the job
        },
        {
            "jobId": "IB20241001160011064", // Unique job identifier
            "status": 2, // The job is in progress
            "failedCount": 0, // Count of objects with errors
            "successfulCount": 88, // Count of successful objects
            "skippedCount": 0, // Count of skipped objects
            "totalCount": 88, // Total count of objects
            "startTime": "2024-10-01T16:00:11Z", // Start time of the job
            "finishTime": "2024-10-02T00:56:42Z", // Finish time of the job
            "duration": "08:56:31", // Duration of the job
            "comments": "" // Comments for the job
        }
    ],
    //For details on nextLink, see 
    "nextLink": "pZ5%2FtiSPUEfNBIK13B%2BPG5WyXm4CBVPocjiPTqZQgfxHHh2isXpr6JU4eK3OYIIUBKLwoh3tWeLFiMd5fn1eytgvIE3C5qgYl1XUUiBcpv2BPmBrJlKXxLOtTDHwvlPCA4wGnuqQEhd5E8NDFbYkWDa5QwLB5mIlFJj607ZxAKvQCG7oG1BLYb0bmRUf6Wz%2B%2FMfzvDPjhV%2Fpz%2F7SwHtj034jcRrkiMkJwXWB" //Link to the next page of results
}
```