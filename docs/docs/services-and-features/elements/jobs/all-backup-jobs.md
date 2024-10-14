# Elements API

Elements provides APIs to retrieve information of your customers, including services, job details, and scan profiles.

## Permissions  

The following permission is required to call the APIs.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](/docs/docs/Use%20AvePoint%20Graph%20Modern%20API.md/#authentication-and-authorization)

| API |Method| Description | Permission Required |
|-----------|--------|-------|--------|
| [/Customers/{Id}/Jobs](#getcustomersidjobs) | GET | Get your customer's job details for the backup services.<br>Note that only the job details for the backup services that the customer has the subscription for are supported. | partner.jobs.read.all |  


## References

### [GET]/Customers/{Id}/Jobs

Get your customer's job details for the backup services.<br>Note that only the job details for the backup services that the customer has the subscription for are supported. 

#### Parameters (Query)
| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned, along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| JobType | The service type of the job. | String |
| JobModule | The service module of the job. | String |
| Status | The job status. | String |
| JobId | The job ID. | String |
| Name | The job name. | String |
| TotalCount | The count of the objects that have been processed by the job. | Int |
| FailedCount | The count of the failed objects. | Int |
| SuccessfulCount | The count of the successful objects. | Int |
| SkippedCount | The count of the skipped objects. | Int |
| WarningCount | The count of the warning objects. | Int |
| BackupSize | The size of the backed-up objects. | String |
| StartTime | The start time of the job. | DateTime |
| EndTime | The end time of the job. | DateTime |
| JobDuration | The job duration. | String |
| LastModifyTime | The last modified time of the job. | DateTime |

