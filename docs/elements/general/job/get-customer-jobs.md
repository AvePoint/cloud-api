# Get the job details of the backup services of a specific customer

Use this API to get the job details of the backup services of a specific customer. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `partner/external/v3/general/customers/{customerId}/jobs/{jobType?}/{jobModule?}`|elements.jobs.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get the job details of the backup services of a specific customer.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `partner/external/v3/general/customers/{customerId}/jobs/{jobType?}/{jobModule?}` | Get the job details of the backup services of a specific customer.|

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| jobType               | The job type of the job.                 | string |
| jobModule     | The job module of the job.       | string |
| status       | The status of the job.      | string |
| jobId | The job id of the job. | string |
| name | The name of the job. | string |
| totalCount | The total count of the job. | string |
| failedCount | The fail count of the job. | string |
| successfulCount | The successful count of the job. | string |
| skippedCount | The skip count of the job. | string |
| warningCount | The warning count the job. | string |
| startTime | The start time of the job. | string |
| endTime | The end time of the job. | string |
| jobDuration | The job duration of the job. | string |
| lastModifyTime | The last modify time of the job. | string |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}/jobs/{jobType?}/{jobModule?}
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
[
    {
        "jobType": "Microsoft 365",
        "jobModule": "SharePoint Online",
        "status": "Successful",
        "jobId": "FB20250911032116214502",
        "name": "N/A",
        "totalCount": "2323",
        "failedCount": "0",
        "successfulCount": "2323",
        "skippedCount": "0",
        "warningCount": "0",
        "backupSize": "0 GB",
        "startTime": "2025-09-11T03:21:16Z",
        "endTime": "2025-09-11T03:38:56Z",
        "jobDuration": "17m39s",
        "lastModifyTime": "2025-09-11T03:38:57Z"
    }
]
```