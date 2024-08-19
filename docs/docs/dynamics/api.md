# Gets job information

> Version v1

Retrieve a list of jobs from Cloud Backup for Dynamics 365.

## Permission

The following permission is required to call this API.

| API method    | Permission required | Permission type |
|-------------------|---------------|----------------------|
| [GetJobs](#method) | Dynamics.ReadWrite.All | Application       |
-------------------------------------------

## Method

| Method | Path | Description |
| --- | --- | --- |
| POST | [/api/OpenApi/GetJobs](#postapiopenapigetjobs) | Gets job collection. |

## Reference Table

| Name | Path | Description |
| --- | --- | --- |
| Dynamics365.Enums.BackupRestoreType | [#/components/schemas/Dynamics365.Enums.BackupRestoreType](#componentsschemasdynamics365enumsbackuprestoretype) |   Sets the job type. |
| Dynamics365.Model.PageModel | [#/components/schemas/Dynamics365.Model.PageModel](#componentsschemasdynamics365modelpagemodel) | Sets the starting page and page size for the job information to retrieve. |
| Dynamics365.Model.Request.JobFilterModel | [#/components/schemas/Dynamics365.Model.Request.JobFilterModel](#componentsschemasdynamics365modelrequestjobfiltermodel) | Sets the job filter, including the startTime, finishTime, status, organizationId, and objectType. |

## Path Details

|Path |Elements|Type|Required?
|---|---|---|---|
|#/components/schemas/Dynamics365.Enums.BackupRestoreType |type|Enum </br>Valid values: </br> - 0 for all.  - 1 for backup.  - 2 for restore.  |Yes|



## [POST]/api/OpenApi/GetJobs

### Request body

- application/json

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

- 200 OK

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