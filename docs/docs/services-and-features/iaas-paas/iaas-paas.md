# Retrieve Job Information

Cloud Backup for IaaS + PaaS provides the `backup/vm/jobs` API to facilitate the retrieval of job-related information through a standardized HTTP GET request. By invoking the `backup/vm/jobs` endpoint, users can access detailed insights and data about specific job reports, enhancing the ability to manage and analyze job information efficiently.  

This API serves as a crucial tool for developers and businesses needing to access job data programmatically, streamlining workflows and enhancing data-driven decision-making.  

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](/Use%20AvePoint%20Graph%20Modern%20API.md/#authentication-and-authorization)

| API     | Permission required | Permission type |
|-------------------|---------------|----------------------|
| `backup/vm/jobs` | PlatformBackup.ReadWrite.All | Application|

## Request  

This section outlines the details on the method used to retrieve job information from Cloud Backup for IaaS + PaaS.  

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `backup/vm/jobs` | Retrieves comprehensive job information. |

## Query Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ------ |
| SearchText | query | Searches by job ID or description. | No | string |
| StartTime | query | Sets a start time (UTC time) for the time range. | No | integer |
| FinishTime | query | Sets an end time (UTC time) for the time range. | No | integer |
| ServiceType | query | Sets the service type of the jobs to get.<ul>  <li>1 - VM</li>  <li>2 - AAD</li><li>4 - AzureFile</li>  <li>8 - FileShare</li><li>16 - BlobStorage</li><li>32 - AKS</li>  <li>64 - APSetting</li><li>128 - Common</li>  <li>256 - AmazonEC2</li><li>512 - AzureSQL</li><li>1024 - AzureDevOps</li></ul> | No | Enum |
| JobType | query | Sets the job types that you want to get.<ul><li> **1** for Backup</li><li> **2** for Restore</li><li> **4** for Export</li><li> **8** for Report</li><li> **16** for VMSync</li><li> **32** for GenIndex</li><li> **33** for AADCompare</li><li> **34** for Retention</li><li> **64** for AADBackup</li><li> **128** for AADRestore</li><li> **256** for AADExport</li><li> **257** for FileSync</li><li> **512** for FileBackup</li><li> **1024** for FileRestore</li><li> **2048** for FileExport</li><li> **4096** for LicenseSync</li><li> **8192** for AOSUpdate</li><li> **16384** for AKSBackup</li><li> **20000** for AKSSync</li><li> **20001** for AKSRestore</li><li> **20002** for APSettingBackup</li><li> **20003** for APSettingExport</li><li> **20004** for APSettingSync</li><li> **20005** for APSettingRestore</li><li> **20006** for ExportCleanUp</li><li> **20007** for EC2Backup</li><li> **20009** for EC2Restore</li><li> **20010** for SQLSync</li><li> **20011** for SQLBackup</li><li> **20012** for SQLRestore</li><li> **20013** for DevOpsBackup</li><li> **20014** for DevOpsRestore</li><li> **20015** for SoftDelete</li><li> **30000** for HardDelete</li><li> **30001** for AdditionalType</li></ul> | No | Enum |
| PageNumber | query | Sets the starting number of the page. The default value is 0. | No | integer |
| PageSize | query | Sets the number of objects to display on one page. The default value is 10. | No | integer |
| SkipToken | query | Sets the skip token got from next link from previous request, if setting this one, PageNumber will be ignored. | No | string |

## Response  

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.  

|Elements|Description | Type|
|---|---|---|
|totalCount||int|
|jobs|A collection of jobs|int|
|jobId|The job ID. ||
|state|Indicates the state of the job.<ul>  <li>0 - NotStarted</li>  <li>1 - InProgress</li>  <li>2 - Successful</li>  <li>4 - Skipped</li>  <li>8 - Exception</li>  <li>16 - Failed</li>  <li>32 - Waiting</li>  <li>64 - Stopped</li></ul> ||
|failedCount|||
|successfulCount|||
|skippedCount|||
|totalCount|||
|startTime|||
|finishTime|||
|duration|||
|comments|||
|errorModel|Returns the request ID, date and the error code. See [HttpStatusCode](/docs/Use%20AvePoint%20Graph%20Modern%20API.md/#http-status-code)||

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant job details in a structured format, enabling easy integration with other systems or applications.  

```
https://graph-us.avepointonlineservices.com/backup/vm/jobs?serviceType=1&jobType=1&pageSize=5&startTime=638527680000000000&finishTime=638633088000000000
```

## Response Sample  

If successful, this method returns a 200 OK response code and a collection of  jobs in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](/docs/Use%20AvePoint%20Graph%20Modern%20API.md/#http-status-code).

```
{
    "totalCount": 51,
    "jobs": [
        {
            "jobId": "IB20240822160048505",
            "state": 2,
            "failedCount": 0,
            "successfulCount": 0,
            "skippedCount": 0,
            "totalCount": 0,
            "startTime": 638599392481859693,
            "finishTime": 638599398999332487,
            "duration": 6517472794,
            "comments": ""
        },
        {
            "jobId": "IB20240821160052944",
            "state": 2,
            "failedCount": 0,
            "successfulCount": 0,
            "skippedCount": 0,
            "totalCount": 0,
            "startTime": 638598528526352169,
            "finishTime": 638598529278694804,
            "duration": 752342635,
            "comments": ""
        },
        {
            "jobId": "IB20240820160110886",
            "state": 2,
            "failedCount": 0,
            "successfulCount": 0,
            "skippedCount": 0,
            "totalCount": 0,
            "startTime": 638597664705763668,
            "finishTime": 638597667419407597,
            "duration": 2713643929,
            "comments": ""
        },
        {
            "jobId": "IB20240819160046802",
            "state": 2,
            "failedCount": 0,
            "successfulCount": 0,
            "skippedCount": 0,
            "totalCount": 0,
            "startTime": 638596800464928012,
            "finishTime": 638596802112439803,
            "duration": 1647511791,
            "comments": ""
        },
        {
            "jobId": "IB20240818160115845",
            "state": 2,
            "failedCount": 0,
            "successfulCount": 0,
            "skippedCount": 0,
            "totalCount": 0,
            "startTime": 638595936755364616,
            "finishTime": 638595939121323200,
            "duration": 2365958584,
            "comments": ""
        }
    ],
    //For details on nextLink, see 
    "nextLink": "pZ5%2FtiSPUEfNBIK13B%2BPG5WyXm4CBVPocjiPTqZQgfxHHh2isXpr6JU4eK3OYIIUBKLwoh3tWeLFiMd5fn1eytgvIE3C5qgYl1XUUiBcpv2BPmBrJlKXxLOtTDHwvlPCA4wGnuqQEhd5E8NDFbYkWDa5QwLB5mIlFJj607ZxAKvQCG7oG1BLYb0bmRUf6Wz%2B%2FMfzvDPjhV%2Fpz%2F7SwHtj034jcRrkiMkJwXWB"
}
```