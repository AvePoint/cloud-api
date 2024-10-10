# Retrieve Job Informatio

The `/cloudbackup/jobs` API endpoint empowers users to seamlessly retrieve job-related information through standardized HTTP GET requests. By leveraging these APIs, users gain comprehensive insights and granular access to job reports, thereby enhancing the ability to manage, analyze, and optimize backup operations with precision and efficiency.  


## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](/Use%20AvePoint%20Graph%20Modern%20API.md/#authentication-and-authorization)

| API   | Permission |
|-------------------|---------------|
|`/cloudbackup/jobs` | microsoft365backup.jobInfo.read.all | 


## API Method

| Method | Path | Description |
| --- | --- | --- |
| GET | `/cloudbackup/jobs` | Gets the job information of Cloud Backup for Microsoft 365. |

-------------------------

## Query Parameters

| Parameter | Description | Type |
| --- | --- | --- |
| StartTime | Sets a start time (UTC time) for the time range. | long |
| FinishTime | Sets an end time (UTC time) for the time range.| long |
| JobType | Sets the job types that you want to get. <br> Defined by `#/components/schemas/BackupJobType`. | Enum <br> **Valid values:** <br> 0 (for All) <br> 1 (for Backup) <br> 2 (for Restore) <br> 3 (for Export) <br> 4 (for Delete) <br> 5 (for Retention) |
| ObjectType | Sets the service type of the jobs to get. <br> Defined by `#/components/schemas/CloudBackupJobObjectType`. | Enum <br> **Valid values:** <br> 0 (for All) <br> 1 (for Exchange Online) <br> 2 (for  SharePoint Online) <br> 3 (for OneDrive) <br> 4 (for Microsoft 365 Groups) <br> 5 (for Project Online) <br> 6 (for Public Folder) <br> 7 (Teams) <br> 8 (Viva Engage) <br> 9 (Teams Chat) <br> 10 (Power BI) <br> 11 (Power Automate) <br> 12 (Power Apps) |
| JobState | Sets the job status. <br> Defined by `#/components/schemas/CloudBackupJobState` |Enum <br> **Valid values:** <br> 0 (for All) <br> 1 (for In Progress) <br> 2 (for Finished) <br> 3 (for Failed) <br> 4 (for Finished with Exception) <br> 5 (for Partially Finished)|
| PageIndex|	Sets the starting number of the page to get the jobs. <br> The default value is 0.| int |
| PageSize|	Sets the number of jobs to display on one page. <br> The default value is 10. | int |

## Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

**Retrieved result:**

| Response | Description | Type |
| --- | --- | --- |
| TotalCount | The total count of the retrieved jobs | int |
| Jobs | A list of jobs | List |
| NextLink | Reference to the next page of results | string |

**Job summary:**

| Response | Description | Type |
| --- | --- | --- |
| Id | Job ID | string |
| State | Job status | string |
| StartTime | Job started time | long |
| FinishTime | Job finished time | long |
| Duration | Duration | long |
| BackupDetails | Job details | int |

**Backup details:**

| Response | Description | Type |
| --- | --- | --- |
| TotalCount | Total count | long |
| FailedCount | Number of failed objects | long |
| SuccessfulCount | Number of successful objects | long |
| SkippedCount| Number of skipped objects | long |

## Request Example (`application/json`):

This section outlines the structure of a request to retrieve job details. The request can include options parameters to filter and paginate results, allowing you to specify time ranges, job types, and statuses.

```ts
{
  StartTime?: long
  FinishTime?: long.
  JobType?: "2" // Reference to #components/schemas/BackupJobType schema.
  ObjectType?: "1" // Reference to #components/schemas/CloudBackupJobObjectType schema.
  JobState?: "0" // Reference to #components/schemas/CloudBackupJobState schema
  PageIndex?: int
  PageSize?: int
}
```

## Response Example  

The response provides detailed information about the requested job, including total counts and individual job details. It allows you to review job states, durations, and backup outcomes.  

```ts
{
  TotalCount?: int
  Jobs:[
  {  
    Id?: string 
    State?: string
    StartTime?: long
    FinishTime?: long
    Duration?: long
    BackupDetails?: 
    {
      TotalCount?: long
      FailedCount?: long
      SuccessfulCount?: long
      SkippedCount?: long
    }
  }
  ]
}
```
