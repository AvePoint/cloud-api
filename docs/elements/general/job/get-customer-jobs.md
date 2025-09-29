# Retrieve Job Details of Backup Services for a Customer

Use this API to retrieve the job details of the backup services for a specific customer.

 ## Permission

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](../../../elements/register-app.md).

| API | Permission  |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/avpt-products/jobs/batch`|elements.jobs.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to retrieve the job details of the backup services for a specific customer.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `/partner/external/v3/general/customers/{customerId}/avpt-products/jobs/batch` | Retrieve the job details of the backup services for a specific customer.|

## Query Parameters

This section outlines the parameters that allow users to specify pagination.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The starting number of the page to get the violated objects. The default value is 1. | integer | No |
| pageSize | The number of objects to display on one page. The default value is 50 and the maximum value allowed is 100. | integer | No |

## Request Body Parameters

This section outlines the request body required to specify which backup service you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| jobType | The service type of the job to be retrieved. | integer | No |
| jobModule | The module of the job to be retrieved. | integer | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| jobType               | The service type of the job.<ul><li>**0** - Microsoft 365 Scan</li><li>**7** - Microsoft 365</li><li>**10** - Google Workspace Scan</li><li>**11** - Google Workspace</li><li>**12** - IaaS + PaaS</li><li>**15** - Salesforce</li><li>**16** - Dynamics 365</li></ul>                 | integer |
| jobModule     | The module of the job. <ul><li>**0** - None</li><li>**1** - Granular Backup and Restore</li><li>**2** - Exchange Online Backup and Restore</li><li>**3** - Report Center</li><li>**4** - Content Management</li><li>**5** - Deployment</li><li>**6** - Replicator</li><li>**7** - Administrator</li><li>**8** - Archiver</li><li>**9** - Cloud App Admin</li><li>**10** - Retention</li><li>**302** - SharePoint Online</li><li>**303** - Exchange Online</li><li>**304** - Microsoft 365 Groups</li><li>**305** - OneDrive</li><li>**306** - Project Online</li><li>**307** - Exchange Online Public Folder</li><li>**308** - Microsoft Teams</li><li>**309** - Archiver</li><li>**310** - Power BI</li><li>**311** - Power Automate</li><li>**312** - Power Apps</li><li>**355** - Cloud Backup for Azure</li><li>**356** - Azure Virtual Machine</li><li>**357** - Disk</li><li>**358** - Microsoft Entra ID</li><li>**359** - Storage</li><li>**360** - Admin Portal Settings</li><li>**361** - Amazon EC2</li><li>**362** - Azure SQL</li><li>**363** - Dev Ops</li><li>**364** - Microsoft Entra ID B2C</li><li>**365** - Azure SQL Backup</li><li>**366** - Google Virtual Machine Instance</li><li>**401** - Dynamics 365</li><li>**402** - Viva Engage</li><li>**501** - Gmail</li><li>**502** - Calendar</li><li>**503** - Contacts</li><li>**504** - Drive</li><li>**505** - Shared Drives</li><li>**506** - Google Classroom</li><li>**507** - Chat</li><li>**508** - Google Directory</li><li>**550** - Dynamics CRM Backup</li><li>**551** - Dynamics Unified Operations Backup</li></ul>      | integer |
| status       | The status of the job. <ul><li>**0** - None</li><li>**1** - Running</li><li>**2** - Finished</li><li>**3** - Failed</li><li>**4** - Finished with exception</li><li>**5** - Skipped</li><li>**6** - Pending</li><li>**7** - Failed to start</li><li>**8** - Canceled</li><li>**9** - Rejected</li><li>**10** - Stopped</li><li>**11** - Not scanned</li><li>**12** - Disabled</li><li>**13** - Not started</li><li>**14** - Waiting for configuration</li></ul>     | integer |
| jobId | The ID of the job. | string |
| name | The name of the job. | string |
| totalCount | The number of the objects that have been processed by the job. | string |
| failedCount | The number of failed objects. | string |
| successfulCount | The number of successful objects. | string |
| skippedCount | The number of skipped objects. | string |
| warningCount | The number of warning objects. | string |
| startTime | The start time of the job. | string |
| endTime | The end time of the job. | string |
| jobDuration | The duration of the job. | string |
| lastModifyTime | The last modified time of the job. | string |

## Request Sample
To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/caf9****-2cc6-****-b04b-794c****5ea3/avpt-products/jobs/batch
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](../../Use-AvePoint-Graph-API.md#http-status-code).
```json
{
    "data": [
        {
            "jobType": 7, // The type of the job: 7 represents Microsoft 365
            "jobModule": 304, // The module of the job: 304 represents Microsoft 365 Groups
            "status": 3, // The status of the job. 3 represents failed
            "jobId": "FB20250911032116214502", // The ID of the job
            "name": "N/A", // The name of the job
            "totalCount": "2323", // The number of the objects that have been processed by the job
            "failedCount": "0", // The number of failed objects
            "successfulCount": "2323", // The number of successful objects
            "skippedCount": "0", // The number of skipped objects
            "warningCount": "0", // The number of warning objects
            "backupSize": "0 GB", // The backup size of the job
            "startTime": "2025-09-11T03:21:16Z", // The start time of the job
            "endTime": "2025-09-11T03:38:56Z", // The end time of the job
            "jobDuration": "17m39s", // The duration of the job
            "lastModifyTime": "2025-09-11T03:38:57Z" // The last modified time of the job
        }
    ],
    "metadata": {
        "pageIndex": 1,
        "pageSize": 50,
        "totalCount": 2
    }
}
```