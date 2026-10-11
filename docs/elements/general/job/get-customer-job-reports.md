# Retrieve Job Report Details

Use this API to retrieve the backup job report details of the Cloud Backup for Microsoft 365 service of a specific customer. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../../elements/register-app.md).


| API | Permission  |
|-----------|--------|
| `partner/external/v3/general/customers/{customerId}/jobs/{jobId}/report-details`|elements.jobs.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve the backup job report details of Cloud Backup for Microsoft 365 of a specific customer.

| Method | Endpoint | Description |
|-----------|--------|------------|
| GET | `partner/external/v3/general/customers/{customerId}/jobs/{jobId}/report-details` | Retrieves the backup job report details of Cloud Backup for Microsoft 365 of a specific customer.|

## Request

This section outlines the parameters required to specify which customer and job you want to retrieve.
 
| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| customerId    | The ID of the customer. | string | Yes |
| jobId | The ID of the job. | string | Yes |
| pageSize | The page index for range paging (1, 1000). | integer | Yes |
| skipToken | The next page token. | string | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Field | Description | Type |
| --- | --- | --- |
| data    | The information of the backup job report.     | `List<JobReportDetails>` |
| metadata.skipToken    | The page size used for the result.         | string |
| metadata.totalCount    | The total number of protected objects.         | string |

### Job Report Information
 
| Field | Description | Type |
| --- | --- | --- |
| title    | The title of the job.            | string |
| type     | The type of the job.<ul><li>**1** - Mailbox</li><li>**2** - Site Collection</li><li>**17** - User</li><li>**20** - Canvas</li><li>**21** - Workspace</li><li>**23** - Flow</li><li>**24** - Agent</li><li>**25** - Viva Engage Metadata</li><li>**26** - Office 365 Group Metadata</li><li>**27** - Teams Metadata</li></ul>       | integer |
| sourceObjectLocation       | The source object location of the job.      | string |
| container | The container of the job. | string |
| size | The size of the job. | integer |
| status | The status of the job:<ul><li>**0** - Success</li><li>**1** - Failed</li><li>**2** - Skipped</li><li>**3** - Filtered</li><li>**4** - Warning</li></ul> | integer |
| finishTime | The finish time of the job. | string |
| comment | The comment of the job. | string |
| errorCode | The error code of the job. | string |

## Request Sample
To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/3b320e95-****-****-****-5971dc0a6716/jobs/CFB20260914161737927794/report-details?pageSize=1
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
{
    "data": [
        {
            "title": "user@domain.com", // The title of the backup job
            "type": 17, // The type of the backup job
            "sourceObjectLocation": "user@domain.com", // The source object location of the backup job
            "container": "Default Microsoft 365 User Container", // The container of the backup job
            "size": 0, // The size of the backup job
            "status": 1, // The status of the backup job
            "finishTime": "2026-09-14T16:17:38.6017245Z", // The finish time of the backup job
            "comment": "Failed to execute backend request, status code: BadGateway, internal error code:BadGateway", // The comment of the backup job
            "errorCode": "" // The error code of the backup job
        }
    ],
    "metadata": {
        "skipToken": "||1%2152%21QmFja3VwU3VtbWFyeV9DRkIyMDI2MDkxNDE2MTczNzkyNzc5NA--%201%2176%21U2tpcGVkX09mZmljZTM2NVVzZXJfMDI3OGU4NDYtZDUyNS00ODc0LTlmZDAtNzgzMmNkOGE4M2Y0", // The skip token for pagination
        "totalCount": 1 // The total number of protected objects
    }
}
```