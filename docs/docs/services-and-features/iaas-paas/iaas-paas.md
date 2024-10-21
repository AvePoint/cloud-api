# Retrieve Job Information

Get the job-related information (`backup/vm/jobs` navigation property) from Cloud Backup for IaaS + PaaS. By invoking the `backup/vm/jobs` endpoint, users can access detailed insights and data about specific job reports, enhancing the ability to manage and analyze job information efficiently.   

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API     | Permission required | Permission type |
|-------------------|---------------|----------------------|
| `backup/vm/jobs` | PlatformBackup.ReadWrite.All | Application|

## Request  

This section outlines the HTTP method and endpoint used to retrieve job information. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `backup/vm/jobs` | Retrieves comprehensive job information. |

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify time ranges, service types, and other criteria to filter the results effectively.

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ------ |
| SearchText | query | Searches by job ID or description. | No | string |
| StartTime | query | Sets a start time (UTC time) for the time range. | No | integer |
| FinishTime | query | Sets an end time (UTC time) for the time range. | No | integer |
| ServiceType | query | Sets the service type of the jobs to get.<ul>  <li> **1** for VM</li>  <li> **2** for AAD</li><li> **4** for AzureFile</li>  <li> **8** for FileShare</li><li> **16** for BlobStorage</li><li> **32** for AKS</li>  <li> **64** for APSetting</li><li> **128** for Common</li>  <li> **256** for AmazonEC2</li><li> **512** for AzureSQL</li><li> **1024** for AzureDevOps</li></ul> | No | Enum |
| JobType | query | Sets the job types that you want to get.<ul><li> **1** for Backup</li><li> **2** for Restore</li><li> **4** for Export</li><li> **8** for Report</li><li> **16** for VMSync</li><li> **32** for GenIndex</li><li> **33** for AADCompare</li><li> **34** for Retention</li><li> **64** for AADBackup</li><li> **128** for AADRestore</li><li> **256** for AADExport</li><li> **257** for FileSync</li><li> **512** for FileBackup</li><li> **1024** for FileRestore</li><li> **2048** for FileExport</li><li> **4096** for LicenseSync</li><li> **8192** for AOSUpdate</li><li> **16384** for AKSBackup</li><li> **20000** for AKSSync</li><li> **20001** for AKSRestore</li><li> **20002** for APSettingBackup</li><li> **20003** for APSettingExport</li><li> **20004** for APSettingSync</li><li> **20005** for APSettingRestore</li><li> **20006** for ExportCleanUp</li><li> **20007** for EC2Backup</li><li> **20009** for EC2Restore</li><li> **20010** for SQLSync</li><li> **20011** for SQLBackup</li><li> **20012** for SQLRestore</li><li> **20013** for DevOpsBackup</li><li> **20014** for DevOpsRestore</li><li> **20015** for SoftDelete</li><li> **30000** for HardDelete</li><li> **30001** for AdditionalType</li></ul> | No | Enum |
| PageNumber | query | Sets the starting number of the page. The default value is 0. | No | integer |
| PageSize | query | Sets the number of objects to display on one page. The default value is 10. | No | integer |
| SkipToken | query | Sets the skip token got from next link from previous request, if setting this one, PageNumber will be ignored. | No | string |

## Response  

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.  

|Elements|Description | Type|
|---|---|---|
|totalCount|Total count of jobs matching the query parameters.|integer|
|jobs|A collection of jobs.|integer|
|jobId|Unique identifier for the job. |string|
|state|Indicates the state of the job.<ul>  <li>**0** for Not Started</li>  <li>**1** for In Progress</li>  <li>**2** for Successful</li>  <li>**4** for Skipped</li>  <li>**8** for Exception</li>  <li>**16** for Failed</li>  <li>**32** for Waiting</li>  <li>**64** for Stopped</li></ul> |Enum|
|failedCount|Count of objects with errors.|integer|
|successfulCount|Count of objects successfully proceed.|integer|
|skippedCount|Count of objects skipped during processing.|integer|
|totalCount|Total count of objects in the job.|integer|
|startTime|The start time of the job.|integer|
|finishTime|The end time of the job.|integer|
|duration|Duration of the job.|integer|
|comments|Comments for the job.|string|
|errorModel|Returns the request ID, date and the error code. See [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).|string|
|nextlink|Returns the link to the next page of results.|string|

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant job details in a structured format, enabling easy integration with other systems or applications.  

```json
https://graph-us.avepointonlineservices.com/backup/vm/jobs?serviceType=1&jobType=1&pageSize=5&startTime=638527680000000000&finishTime=638633088000000000
```

## Response Sample  

If successful, this method returns a 200 OK response code and a collection of  jobs in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](/docs/docs/Use%20AvePoint%20Graph%20Modern%20API.md/#http-status-code).

```json
{
    "totalCount": 51, // Total count of jobs
    "jobs": [
        {
            "jobId": "IB20240822160048505", // Unique job identifier
            "state": 2, // The job is in progress
            "failedCount": 0, // Count of objects with errors
            "successfulCount": 0, // Count of successful objects
            "skippedCount": 0, // Count of skipped objects
            "totalCount": 0, // Total count of objects
            "startTime": 638599392481859693, // Start time of the job
            "finishTime": 638599398999332487, // Finish time of the job
            "duration": 6517472794, // Duration of the job
            "comments": "" // Comments for the job
        },
        {
            "jobId": "IB20240821160052944", // Unique job identifier 
            "state": 2, // The job is in progress
            "failedCount": 0, // Count of objects with errors
            "successfulCount": 0, // Count of successful objects
            "skippedCount": 0, // Count of skipped objects
            "totalCount": 0, // Total count of objects
            "startTime": 638598528526352169, // Start time of the job
            "finishTime": 638598529278694804, // Finish time of the job
            "duration": 752342635, // Duration of the job
            "comments": "" // Comments for the job
        },
        {
            "jobId": "IB20240820160110886", // Unique job identifier
            "state": 2, // The job is in progress
            "failedCount": 0, // Count of objects with errors
            "successfulCount": 0, // Count of successful objects
            "skippedCount": 0, // Count of skipped objects
            "totalCount": 0, // Total count of objects
            "startTime": 638597664705763668, // Start time of the job
            "finishTime": 638597667419407597, // Finish time of the job
            "duration": 2713643929, // Duration of the job
            "comments": "" // Comments for the job
        },
        {
            "jobId": "IB20240819160046802", // Unique job identifier 
            "state": 2, // The job is in progress
            "failedCount": 0, // Count of objects with errors
            "successfulCount": 0, // Count of successful objects
            "skippedCount": 0, // Count of skipped objects
            "totalCount": 0, // Total count of objects
            "startTime": 638596800464928012, // Start time of the job
            "finishTime": 638596802112439803, // Finish time of the job
            "duration": 1647511791, // Duration of the job
            "comments": "" // Comments for the job
        },
        {
            "jobId": "IB20240818160115845", // Unique job identifier
            "state": 2, // The job is in progress
            "failedCount": 0, // Count of objects with errors
            "successfulCount": 0, // Count of successful objects
            "skippedCount": 0, // Count of skipped objects
            "totalCount": 0, // Total count of objects
            "startTime": 638595936755364616, // Start time of the job
            "finishTime": 638595939121323200, // Finish time of the job
            "duration": 2365958584, // Duration of the job
            "comments": "" // Comments for the job
        }
    ],
    //For details on nextLink, see 
    "nextLink": "pZ5%2FtiSPUEfNBIK13B%2BPG5WyXm4CBVPocjiPTqZQgfxHHh2isXpr6JU4eK3OYIIUBKLwoh3tWeLFiMd5fn1eytgvIE3C5qgYl1XUUiBcpv2BPmBrJlKXxLOtTDHwvlPCA4wGnuqQEhd5E8NDFbYkWDa5QwLB5mIlFJj607ZxAKvQCG7oG1BLYb0bmRUf6Wz%2B%2FMfzvDPjhV%2Fpz%2F7SwHtj034jcRrkiMkJwXWB" //Link to the next page of results
}
```