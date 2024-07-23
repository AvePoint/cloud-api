# OpenApi Apis

> Version v1

## Path Table

| Method | Path | Description |
| --- | --- | --- |
| POST | [/api/OpenApi/GetJobs](#postapiopenapigetjobs) |  |

## Reference Table

| Name | Path | Description |
| --- | --- | --- |
| Dynamics365.Enums.BackupRestoreType | [#/components/schemas/Dynamics365.Enums.BackupRestoreType](#componentsschemasdynamics365enumsbackuprestoretype) |  |
| Dynamics365.Model.PageModel | [#/components/schemas/Dynamics365.Model.PageModel](#componentsschemasdynamics365modelpagemodel) |  |
| Dynamics365.Model.Request.JobFilterModel | [#/components/schemas/Dynamics365.Model.Request.JobFilterModel](#componentsschemasdynamics365modelrequestjobfiltermodel) |  |

## Path Details

***

### [POST]/api/OpenApi/GetJobs

#### RequestBody

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

#### Responses

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