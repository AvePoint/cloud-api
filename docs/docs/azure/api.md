# My Title

> Version 1.0.0

## Path Table

| Method | Path | Description |
| --- | --- | --- |
| POST | [/api/public/jobreport](#postapipublicjobreport) | Use this POST api/public/jobreport API to retrieve the job information. |

## Reference Table

| Name | Path | Description |
| --- | --- | --- |
| ReportJobModel | [#/components/schemas/ReportJobModel](#componentsschemasreportjobmodel) | Represents the returned jobs collection. |
| Jobs | [#/components/schemas/Jobs](#componentsschemasjobs) | Represents a job in product. |
| ReportJobRequestModel | [#/components/schemas/ReportJobRequestModel](#componentsschemasreportjobrequestmodel) | Request model of job information. |
| CommonStatus | [#/components/schemas/CommonStatus](#componentsschemascommonstatus) |  |
| JobType | [#/components/schemas/JobType](#componentsschemasjobtype) |  |
| ProductModel | [#/components/schemas/ProductModel](#componentsschemasproductmodel) |  |
| PaginationModel | [#/components/schemas/PaginationModel](#componentsschemaspaginationmodel) | Representing one page information for one request. |

## Path Details

***

### [POST]/api/public/jobreport

- Summary  
Use this POST api/public/jobreport API to retrieve the job information.

#### RequestBody

- application/json

```ts
// Request model of job information.
{
  // Searches by job ID or description.
  searchText?: string
  // Sets a start time (UTC time) for the time range.
  startTime?: integer
  // Sets an end time (UTC time) for the time range.
  finishTime?: integer
  // Sets the service type of the jobs to get.
  serviceType?: #/components/schemas/ProductModel
  // Sets the job types that you want to get.
  jobType?: #/components/schemas/JobType
  // Sets the request page information.
  pagination?: #/components/schemas/PaginationModel
}
```

#### Responses

- 200 If successful, this method returns 200 OK response code and report job object in the response body.

`application/json`

```ts
// Represents the returned jobs collection.
{
  // Total count of current request.
  totalCount?: integer
  // Represents a job in product.
  jobs: {
    // The job Id in current job.
    jobId?: string
    // The job state in current job.
    state?: #/components/schemas/CommonStatus
    // The failed objects count in current job.
    failedCount?: integer
    // The successful objects count in current job.
    successfulCount?: integer
    // The skipped objects count in current job.
    skippedCount?: integer
    // The total objects cunt in current job.
    totalCount?: integer
    // The start time of current job.
    startTime?: integer
    // The end time of current job.
    finishTime?: integer
    // The duration of current job.
    duration?: integer
    // Some comments in current job.
    comments?: string
  }[]
}
```

## References

### #/components/schemas/ReportJobModel

```ts
// Represents the returned jobs collection.
{
  // Total count of current request.
  totalCount?: integer
  // Represents a job in product.
  jobs: {
    // The job Id in current job.
    jobId?: string
    // The job state in current job.
    state?: #/components/schemas/CommonStatus
    // The failed objects count in current job.
    failedCount?: integer
    // The successful objects count in current job.
    successfulCount?: integer
    // The skipped objects count in current job.
    skippedCount?: integer
    // The total objects cunt in current job.
    totalCount?: integer
    // The start time of current job.
    startTime?: integer
    // The end time of current job.
    finishTime?: integer
    // The duration of current job.
    duration?: integer
    // Some comments in current job.
    comments?: string
  }[]
}
```

### #/components/schemas/Jobs

```ts
// Represents a job in product.
{
  // The job Id in current job.
  jobId?: string
  // The job state in current job.
  state?: #/components/schemas/CommonStatus
  // The failed objects count in current job.
  failedCount?: integer
  // The successful objects count in current job.
  successfulCount?: integer
  // The skipped objects count in current job.
  skippedCount?: integer
  // The total objects cunt in current job.
  totalCount?: integer
  // The start time of current job.
  startTime?: integer
  // The end time of current job.
  finishTime?: integer
  // The duration of current job.
  duration?: integer
  // Some comments in current job.
  comments?: string
}
```

### #/components/schemas/ReportJobRequestModel

```ts
// Request model of job information.
{
  // Searches by job ID or description.
  searchText?: string
  // Sets a start time (UTC time) for the time range.
  startTime?: integer
  // Sets an end time (UTC time) for the time range.
  finishTime?: integer
  // Sets the service type of the jobs to get.
  serviceType?: #/components/schemas/ProductModel
  // Sets the job types that you want to get.
  jobType?: #/components/schemas/JobType
  // Sets the request page information.
  pagination?: #/components/schemas/PaginationModel
}
```

### #/components/schemas/CommonStatus

```ts
{
  "type": "integer",
  "description": "",
  "x-enumNames": [
    "NotStarted",
    "InProgress",
    "Successful",
    "Skipped",
    "Exception",
    "Failed",
    "Waiting",
    "Stopped"
  ],
  "enum": [
    0,
    1,
    2,
    4,
    8,
    16,
    32,
    64
  ]
}
```

### #/components/schemas/JobType

```ts
{
  "type": "integer",
  "description": "",
  "x-enumNames": [
    "Backup",
    "Restore",
    "Export",
    "Report",
    "VMSync",
    "Initliaze",
    "GenIndex",
    "AADCompare",
    "Retention",
    "AADBackup",
    "AADRestore",
    "AADExport",
    "FileSync",
    "FileBackup",
    "FileRestore",
    "FileExport",
    "LicenseSync",
    "AOSUpdate",
    "AKSBackup",
    "AKSSync",
    "AKSRestore",
    "APSettingBackup",
    "APSettingExport",
    "APSettingSync",
    "APSettingRestore",
    "ExportCleanUp",
    "EC2Backup",
    "EC2Restore",
    "SQLSync",
    "SQLBackup",
    "SQLRestore",
    "DevOpsBackup",
    "DevOpsRestore",
    "SoftDelete",
    "HardDelete"
  ],
  "enum": [
    1,
    2,
    4,
    8,
    16,
    32,
    33,
    34,
    64,
    128,
    256,
    257,
    512,
    1024,
    2048,
    4096,
    8192,
    16384,
    20000,
    20001,
    20002,
    20003,
    20004,
    20005,
    20006,
    20007,
    20009,
    20010,
    20011,
    20012,
    20013,
    20014,
    20015,
    30000,
    30001
  ]
}
```

### #/components/schemas/ProductModel

```ts
{
  "type": "integer",
  "description": "",
  "x-enumNames": [
    "VM",
    "AAD",
    "AzureFile",
    "FileShare",
    "BlobStorage",
    "AKS",
    "APSetting",
    "Common",
    "AmazonEC2",
    "AzureSQL",
    "AzureDevOps"
  ],
  "enum": [
    1,
    2,
    4,
    8,
    16,
    32,
    64,
    128,
    256,
    512,
    1024
  ]
}
```

### #/components/schemas/PaginationModel

```ts
// Representing one page information for one request.
{
  // Sets the starting number of the page. The default value is 0.
  pageNumber?: integer
  // Sets the number of objects to display on one page. The default value is 10.
  pageSize?: integer
}
```