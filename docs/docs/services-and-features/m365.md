# Cloud Backup for Microsoft 365 Public API

> Version 1.0.0

Gets the job information and the subscription consumption information of Cloud Backup for Microsoft 365.

## Methods

| Method | Path | Description |
| --- | --- | --- |
| GET | [/cloudbackup/jobs](#getcloudbackupjobs) | Gets the job information of Cloud Backup for Microsoft 365. |
| GET | [/cloudbackup/licenseconsumption](#getcloudbackuplicenseconsumption) | Gets the subscription consumption information of Cloud Backup for Microsoft 365. |

## Path Details

### [GET]/cloudbackup/jobs

Gets the job information of Cloud Backup for Microsoft 365.

#### Query Parameters

| Parameter | Description | Type |
| --- | --- | --- |
| StartTime | Sets a start time (UTC time) for the time range. | long |
| FinishTime | Sets an end time (UTC time) for the time range.| long |
| JobType | Sets the job types that you want to get. <br> Defined by `#/components/schemas/BackupJobType`. | Enum <br> **Valid values:** <br> 0 (for All) <br> 1 (for Backup) <br> 2 (for Restore) <br> 3 (for Export) <br> 4 (for Delete) <br> 5 (for Retention) |
| ObjectType | Sets the service type of the jobs to get. <br> Defined by `#/components/schemas/CloudBackupJobObjectType`. | Enum <br> **Valid values:** <br> 0 (for All) <br> 1 (for Exchange Online) <br> 2 (for  SharePoint Online) <br> 3 (for OneDrive) <br> 4 (for Microsoft 365 Groups) <br> 5 (for Project Online) <br> 6 (for Public Folder) <br> 7 (Teams) <br> 8 (Viva Engage) <br> 9 (Teams Chat) <br> 10 (Power BI) <br> 11 (Power Automate) <br> 12 (Power Apps) |
| JobState | Sets the job status. <br> Defined by `#/components/schemas/CloudBackupJobState` |Enum <br> **Valid values:** <br> 0 (for All) <br> 1 (for In Progress) <br> 2 (for Finished) <br> 3 (for Failed) <br> 4 (for Finished with Exception) <br> 5 (for Partially Finished)|
| PageIndex|	Sets the starting number of the page to get the jobs. <br> The default value is 0.| int |
| PageSize|	Sets the number of jobs to display on one page. <br> The default value is 10. | int |
#### Responses

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

#### Example (`application/json`):

- Request

```ts
{
  StartTime?: long
  FinishTime?: long.
  JobType?: #/components/schemas/BackupJobType
  ObjectType?: #/components/schemas/CloudBackupJobObjectType
  JobState?: #/components/schemas/CloudBackupJobState
  PageIndex?: int
  PageSize?: int
}
```

- Response
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

***

### [GET]/cloudbackup/licenseconsumption

Gets the subscription consumption information of Cloud Backup for Microsoft 365.

#### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| OutOfPolicyTime | The UTC that the license got out of policy. | long |
| PurchasedUserSeats | Purchased user seats | int |
| AssignedUserSeats | Assigned user seats | int |
| PurchasedStorageSize | Purchased storage size | int |
| ProtectedSize | Protected size | int |

#### Example (`application/json`):

- Response

```ts
{
  OutOfPolicyTime?: long
  PurchasedUserSeats?: int
  AssignedUserSeats?: int
  PurchasedStorageSize?: int
  ProtectedSize?: int
}
```
