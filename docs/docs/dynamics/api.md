# Gets job information

> Version v1

Retrieve a list of jobs from Cloud Backup for Dynamics 365.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](../).

| API method    | Permission required | Permission type |
|-------------------|---------------|----------------------|
| [GetJobs](#method) | Dynamics.ReadWrite.All | Application       |
-------------------------------------------

## Method

| Method | Path | Description |
| --- | --- | --- |
| POST | [/api/OpenApi/GetJobs](#examples) | Gets job collection. |

## Properties

| Name | Path | Description |
| --- | --- | --- |
| Dynamics365.Enums.BackupRestoreType | [#/components/schemas/Dynamics365.Enums.BackupRestoreType](#componentsschemasdynamics365enumsbackuprestoretype) |   Sets the job type. |
| Dynamics365.Model.PageModel | [#/components/schemas/Dynamics365.Model.PageModel](#componentsschemasdynamics365modelpagemodel) | Sets the starting page and page size for the job information to retrieve. |
| Dynamics365.Model.Request.JobFilterModel | [#/components/schemas/Dynamics365.Model.Request.JobFilterModel](#componentsschemasdynamics365modelrequestjobfiltermodel) | Sets the job filter, including the startTime, finishTime, status, organizationId, and objectType. |

## Property Details

|Property |Elements|Description | Type|Required?|   
|---|---|---|---|---|    
|#/components/schemas/Dynamics365.Enums.BackupRestoreType |type|Sets the job types that you want to get.|Enum </br> Valid values:</br> - 0 for all.</br> - 1 for backup. </br> - 2 for restore.  |Yes|
|#/components/schemas/Dynamics365.Model.PageModel|currentPage|Sets the starting number of the page to get the jobs. The default value is 1.|int|Yes|
||pageSize|Sets the number of jobs to display on one page. The default value is 10.|int|Yes|
|#/components/schemas/Dynamics365.Model.Request.JobFilterModel|startTime|Sets a start time (UTC time) for the time range.|long|Yes|
||finishTime|Sets an end time (UTC time) for the time range.|long|Yes|
||status| Sets the job status.|Enum </br> 2 for In progress</br> 3 for Finished</br>4 for Failed </br>7 for Finished with Exception</br>|Yes|  
||organizationId|Sets the organization that you want to get.|GUID|Yes|
||objectType|Sets the module type of the jobs to get.|Enum|Yes|

## Examples

Refer to the following examples calling this API.

### Request body  

Content-type: application/json

```ts
{
  pageInfo: {
    currentPage?: integer
    pageSize?: integer
  }
  type?: enum[0, 1, 2, 4, 8, 16]
  startTime?: string
  endTime?: string
  status?: integer
  organizationId?: string
  objectType?: integer
}
```

- text/json

```ts
{
  pageInfo: {
    currentPage?: integer
    pageSize?: integer
  }
  type?: enum[0, 1, 2, 4, 8, 16]
  startTime?: string
  endTime?: string
  status?: integer
  organizationId?: string
  objectType?: integer
}
```

- application/*+json

```ts
{
  pageInfo: {
    currentPage?: integer
    pageSize?: integer
  }
  type?: enum[0, 1, 2, 4, 8, 16]
  startTime?: string
  endTime?: string
  status?: integer
  organizationId?: string
  objectType?: integer
}
```

### Responses

If successful, this method returns a 200 OK response code and a collection of  jobs in the response body.

## References

### #/components/schemas/Dynamics365.Enums.BackupRestoreType

```ts
{
  "enum": [
    0,
    1,
    2,
    4,
    8,
    16
  ],
  "type": "integer",
  "format": "int32"
}
```

### #/components/schemas/Dynamics365.Model.PageModel

```ts
{
  currentPage?: integer
  pageSize?: integer
}
```

### #/components/schemas/Dynamics365.Model.Request.JobFilterModel

```ts
{
  pageInfo: {
    currentPage?: integer
    pageSize?: integer
  }
  type?: enum[0, 1, 2, 4, 8, 16]
  startTime?: string
  endTime?: string
  status?: integer
  organizationId?: string
  objectType?: integer
}
```
