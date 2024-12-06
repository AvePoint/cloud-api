# Retrieve Specific Job Type and Module of Backup Services

Use this API to retrieve your customer's job details for a specific job type and module of backup services, including Cloud Backup for Microsoft 365, Cloud Backup for Google Workspace, Cloud Backup for IaaS PaaS, Cloud Backup for Dynamics 365, and Cloud Backup for Salesforce.
<br>This API is intended specifically for customers who have subscribed to these services.

## Permissions  

The following permission is required to call the API.  
You must register an app through Elements for Partners > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `/partner/customers/{Id}/jobs/jobType/{JobType}/jobModule/{JobModule}` | partner.jobs.read.all  |  

## Request 

This section provides details on the HTTP method and endpoint used to retrieve your customer's job details for a specific job type and module of backup services.

| Method| Endpoint | Description |
|-----------|--------|-------|
| GET | `/partner/customers/{Id}/jobs/jobType/{JobType}/jobModule/{JobModule}` | Retrieves your customer's job details for a specific job type and module of the backup services. |

## Query Parameters

This section outlines the parameters required to specify the job type and module of backup services that you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| Id | The tenant owner ID of the customer. | String | Yes |
| JobType | The service type of the job. | String | Yes |
| JobModule | The service module of the job. | String | Yes |

## Responses

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| jobType | The service type of the job. | String |
| jobModule | The service module of the job. | String |
| status | The job status. | String |
| jobId | The job ID. | String |
| name | The job name. | String |
| totalCount | The count of the objects that have been processed by the job. | Int |
| failedCount | The count of the failed objects. | Int |
| successfulCount | The count of the successful objects. | Int |
| skippedCount | The count of the skipped objects. | Int |
| warningCount | The count of the warning objects. | Int |
| backupSize | The size of the backed-up objects. | String |
| startTime | The start time of the job. | DateTime |
| endTime | The end time of the job. | DateTime |
| jobDuration | The job duration. | String |
| lastModifyTime | The last modified time of the job. | DateTime |

***
## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. 

```json
https://graph.avepointonlineservices.com/partner/customers/00427fbc-8832-46cf-a1d2-582fa46ec638/jobs/jobType/Microsoft 365/jobModule/SharePoint Online
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](/docs/use-avepoint-graph-modern-API/##HTTP-Status-Code)[HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).

```json 
{
    "@odata.context": "https://graph.avepointonlineservices.com/partner/$metadata#Collection(Portal.Api.Model.BackUpJob)",
    "value": [
        {
            "jobType": "Microsoft 365", // The service type of the job
            "jobModule": "SharePoint Online", // The service module of the job
            "status": "Not Finished", // The job status
            "jobId": "N/A", // The job ID
            "name": "N/A", // The job name
            "totalCount": "0", // The count of the objects that have been processed by the job
            "failedCount": "0", // The count of the failed objects
            "successfulCount": "0", // The count of the successful objects
            "skippedCount": "0", // The count of the skipped objects
            "warningCount": "0", // The count of the warning objects
            "backupSize": "0 GB", // The size of the backed-up objects
            "startTime": "N/A", // The start time of the job
            "endTime": "N/A", // The end time of the job
            "jobDuration": "N/A", //The job duration
            "lastModifyTime": "N/A" // The last modified time of the job
        }
    ]
}
```