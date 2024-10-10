# Retrieve Job Information for Cloud Backup for IaaS + PaaS

Cloud Backup for IaaS + PaaS provides the `backup/vm/jobs` API to facilitate the retrieval of job-related information through a standardized HTTP GET request. By invoking the `backup/vm/jobs` endpoint, users can access detailed insights and data about specific job reports, enhancing the ability to manage and analyze job information efficiently.  

This API serves as a crucial tool for developers and businesses needing to access job data programmatically, streamlining workflows and enhancing data-driven decision-making.  

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](/docs/index.md/#authentication-and-authorization)

| API method    | Permission required | Permission type |
|-------------------|---------------|----------------------|
| [Jobs](#method) | PlatformBackup.ReadWrite.All | Application|

## API Method

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | [backup/vm/jobs](#postapipublicjobreport) | Retrieves comprehensive job information. |

## Reference Table

| Name | Reference | Description |
| --- | --- | --- |
| ReportJobModel | [#/components/schemas/ReportJobModel](#componentsschemasreportjobmodel) | Represents the returned jobs collection. |
| Jobs | [#/components/schemas/Jobs](#componentsschemasjobs) | Represents a job. |
| CommonStatus | [#/components/schemas/CommonStatus](#componentsschemascommonstatus) | Represents various statuses a job can have. <br> <ul><li> NotStarted - 0</li><li>InProgress - 1</li><li>Successful - 2</li><li>Skipped - 4</li><li>Exception - 8</li><li>Failed - 16</li><li>Waiting - 32</li><li>Stopped - 64</li></ul>|
| JobType | [#/components/schemas/JobType](#componentsschemasjobtype) | Represents different types of jobs. <br><ul><li>Backup - 1 </li><li>Restore - 2</li><li>Export - 4</li><li>Report - 8</li></ul>Additional types such as VMSync, GenIndex, AADBackup, AADCompare, etc. are also included, representing a wide range of job operations. See the reference|
| ProductModel | [#/components/schemas/ProductModel](#componentsschemasproductmodel) | Represents different service types associated with jobs.<br><ul><li>VM - 1</li><li>AAD - 2</li><li>AzureFile - 4</li><li>FileShare - 8</li><li>BlobStorage - 16</li><li>APSetting - 64</li><li>Common - 128</li><li>AmazonEC2 - 256</li><li>AzureSQL - 521</li><li>AzureDevOps - 1024</li></ul> |
| ErrorModel | [#/components/schemas/ErrorModel](#componentsschemaserrormodel) | Represents the returned error. |
| HttpStatusCode | [#/components/schemas/HttpStatusCode](#componentsschemashttpstatuscode) | Represents the returned of various HTTP status code. <br> <ul><li> OK - 200</li><li>BadRequest - 400</li><li>InternalServerError - 500</li></ul>|

## Request Details

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant job details in a structured format, enabling easy integration with other systems or applications.  

### [GET] backup/vm/jobs

Use this GET backup/vm/jobs API to retrieve the job information.

### Query parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ------ |
| SearchText | query | Searches by job ID or description. | No | string |
| StartTime | query | Sets a start time (UTC time) for the time range. | No | integer |
| FinishTime | query | Sets an end time (UTC time) for the time range. | No | integer |
| ServiceType | query | Sets the service type of the jobs to get. | No | [#/components/schemas/ProductModel](#componentsschemasproductmodel) |
| JobType | query | Sets the job types that you want to get. | No | [#/components/schemas/JobType](#componentsschemasjobtype) |
| PageNumber | query | Sets the starting number of the page. The default value is 0. | No | integer |
| PageSize | query | Sets the number of objects to display on one page. The default value is 10. | No | integer |
| SkipToken | query | Sets the skip token got from next link from previous request, if setting this one, PageNumber will be ignored. | No | string |

### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.  

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
  // Next link for request, set the SkipToken for next request.
  nextLink?: string
}
```

## References

### #/components/schemas/ReportJobModel

The `ReportJobModel` is a schema component that defines the structure of a collection of jobs returned by the API. It provides a comprehensive overview of job-related metrics and statuses, encapsulating essential details within a structured format.

```ts
// Represents the returned jobs collection.
{
  // Represents the total number of jobs for the current request.
  totalCount?: integer
  // Jobs array. Contains multiple job objects, each with the following attributes:
  jobs: {
    // Indicates the job ID of current job.
    jobId?: string
    // Indicates the state of the job.
    state?: #/components/schemas/CommonStatus
    // Indicates the number of the errored objects within the job.
    failedCount?: integer
    // Indicates the number of the successful objects within the job.
    successfulCount?: integer
    // Indicates the number of the skipped objects within the job.
    skippedCount?: integer
    // Indicates the total number of objects in the job.
    totalCount?: integer
    // The start time of the job.
    startTime?: integer
    // The end time of the job.
    finishTime?: integer
    // The duration of the job.
    duration?: integer
    // Any additional notes or comments regarding the job.
    comments?: string
  }
  // Next link for request, set the SkipToken for next request.
  nextLink?: string
}
```

### #/components/schemas/Jobs

The `Jobs` component represents a job within the Cloud Backup for IaaS + PasS product.

```ts
// Represents a job in product.
{
  // The job ID.
  jobId?: string
  // A reference to the CommonStatus schema, indicating the current state of the job.
  state?: #/components/schemas/CommonStatus
  // Indicates the number of the failed objects within the job.
  failedCount?: integer
  // Indicates the number of the successful objects within the job.
  successfulCount?: integer
  // Indicates the number of the skipped objects within the job.
  skippedCount?: integer
  // Indicates the the total number of the objects in the job.
  totalCount?: integer
  // The start time of the job.
  startTime?: integer
  // The end time of the job.
  finishTime?: integer
  // The duration of the job.
  duration?: integer
  // Any additional notes or comments regarding to this job.
  comments?: string
}
```

### #/components/schemas/CommonStatus

The `CommonStatus` schema defines various statuses a job can have. It uses an integer type to represent the status, with each integer corresponding to a specific status. These statuses help track the progress and outcome of jobs within the system.

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

The `JobType` schema categorizes different types of jobs using an integer representation. Each integer corresponds to a specific job type, allowing for precise identification and filtering.  

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

The `ProductModel` schema specifies different service types associated with jobs. Each service type is represented by an integer, aiding in categorization and filtering based on the service involved.  

```ts
{
  "type": "integer",
  "description": "Specifies the service types for the jobs to retrieve.",
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

### #/components/schemas/ErrorModel

The `ErrorModel` schema returned when request has problems.  

```ts
// Represents the error information for the request results.
{
  // Represents the current request id.
  requestId?: string
  // Represents the current date time.
  date?: string
  // A reference to the HttpStatusCode schema, indicating the error code of the result.
  statusCode?: #/components/schemas/HttpStatusCode
}
```

### #/components/schemas/HttpStatusCode

The `HttpStatusCode` schema specifies different http status code associated with result.

```ts
{
  "type": "integer",
  "description": "Specifies different http status code associated with result.",
  "x-enumNames": [
    "OK",
    "BadRequest",
    "InternalServerError"
  ],
  "enum": [
    200,
    400,
    500
  ]
}
```