# My Title

> Version 1.0.0

## Path Table

| Method | Path | Description |
| --- | --- | --- |
| POST | [/api/PublicApi/cloudbackup/jobs](#postapipublicapicloudbackupjobs) | This scope contains the APIs which get the job basic info in Cloud Backup for Microsoft 365. |
| GET | [/api/PublicApi/cloudbackup/licenseconsumption](#getapipublicapicloudbackuplicenseconsumption) | This scope contains the APIs which get the subscription consumption info in Cloud Backup for Microsoft 365. |

## Reference Table

| Name | Description | Type | Required
| --- | --- | --- | --- |
| JobType | Sets the job types that you want to get. | [#/components/schemas/BackupJobType](#componentsschemasbackupjobtype) | Yes
| ObjectType | Sets the service type of the jobs to get. | [#/components/schemas/CloudBackupJobObjectType](#componentsschemascloudbackupjobobjecttype)  | Yes
| JobState | Sets the job status | [#/components/schemas/CloudBackupJobState](#componentsschemascloudbackupjobstate)  | Yes


## Path Details

***

### [POST]/api/PublicApi/cloudbackup/jobs

- Summary  
This scope contains the APIs which get the job basic info in Cloud Backup for Microsoft 365.

#### RequestBody

- application/json

```ts
// Request model.
{
  // Sets a start time (UTC time) for the time range.
  StartTime?: long
  // Sets an end time (UTC time) for the time range.
  FinishTime?: long
  // Sets the job types that you want to get.
  JobType?: #/components/schemas/BackupJobType
   // Sets the service type of the jobs to get.
  ObjectType?: #/components/schemas/CloudBackupJobObjectType
   // Sets the job status
  JobState?: #/components/schemas/CloudBackupJobState
  // Sets the starting number of the page to get the jobs. The default value is 0.
  PageIndex?: int
  // Sets the number of jobs to display on one page. The default value is 10.
  PageSize?: int
}
```

#### Responses

- 200 If successful, this method returns 200 OK response code and job basic info in the response body.

`application/json`

```ts
{
  // The total count of the retrieved jobs
  TotalCount?: int
  // Represents job list
  jobs: [
  {
    // Job ID
    Id?: string
    // Job status
    State?: string
    // Job started time
    StartTime?: long
    // Job finished time
    FinishTime?: long
     // Duration
    Duration?: long
     // Job details
    BackupDetails?: 
    {
      // Total count
      TotalCount?: long
       // Number of failed objects
      FailedCount?: long
       // Number of successful objects
      SuccessfulCount?: long
       // Number of skipped objects
      SkippedCount?: long
    }
  }
  ]
}
```

***

### [GET]/api/PublicApi/cloudbackup/licenseconsumption

- Summary  
This scope contains the APIs which get the subscription consumption info in Cloud Backup for Microsoft 365.

#### Responses

- 200 If successful, this method returns 200 OK response code and cloud backup license consumptions in the response body.

```ts
// LicenseConsumption model.
{
  // The UTC that the license got out of policy.
  OutOfPolicyTime?: long
  // Purchased user seats
  PurchasedUserSeats?: int
  // Assigned user seats
  AssignedUserSeats?: int
  // TPurchased storage size
  PurchasedStorageSize?: int
  // Protected size
  ProtectedSize?: int
}
```



## References

### #/components/schemas/BackupJobType

```ts
{
  "type": "integer",
  "description": "",
  "x-enumNames": [
    "All",
    "Backup",
    "Restore",
    "Export",
    "Delete",
    "Retention"
  ],
  "enum": [
    0,
    1,
    2,
    3,
    4,
    5
  ]
}
```
### #/components/schemas/CloudBackupJobObjectType

```ts
{
  "type": "integer",
  "description": "",
  "x-enumNames": [
    "All",
    "ExchangeOnline",
    "SharePointOnline",
    "OneDrive",
    "Groups",
    "ProjectOnline",
    "PublicFolder",
    "Teams",
    "YammerGroup",
    "PersonalChat",
    "PowerBI",
    "PowerAutomate",
    "PowerApps"
  ],
  "enum": [
    0,
    1,
    2,
    3,
    4,
    5,
    6,
    7,
    8,
    9,
    10,
    11,
    12
  ]
}
```

### #/components/schemas/CloudBackupJobState

```ts
{
 "type": "integer",
  "description": "",
  "x-enumNames": [
    "All",
    "InProgress",
    "Finished",
    "Failed",
    "FinishedException",
    "PartiallyFinished"
  ],
  "enum": [
    0,
    1,
    2,
    3,
    4,
    5
  ]
}
```
