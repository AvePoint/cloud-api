# Get the job details of the backup services of a specific customer

Use this API to get the job details of the backup services of a specific customer. 

 ## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [App Registration](https://cdn.avepoint.com/assets/apelements-webhelp/avepoint-elements-for-partners/index.htm#!Documents/appregistration.htm).

| API | Permission  |
|-----------|--------|
| `partner/external/v3/general/customers/{customerId}/jobs`|elements.jobs.read.all|  

## Request

This section outlines the details of the HTTP method and endpoint used to get the job details of the backup services of a specific customer.

| Method | Endpoint | Description |
|-----------|--------|------------|
| POST | `partner/external/v3/general/customers/{customerId}/jobs` | Get the job details of the backup services of a specific customer.|

## Query Parameters

This section outlines the parameters optional required to specify paging information about the backup services you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| pageIndex | The page number of the data which will be retrieve, the default value is 1. | integer | No |
| pageSize | The number of customers API will retrieved in a time, the default value is 100. | integer | No |

## Request Body

This section outlines the request body required to specify which backup service you want to retrieve.

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| jobType | The job type of the job to be retrived | integer | No |
| jobModule | The job module of the job to be retrived | integer | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
 
| Field | Description | Type |
| --- | --- | --- |
| jobType               | The job type of the job.<ul><li>**0** - Microsoft 365 Scan</li><li>**7** - Microsoft 365</li><li>**10** - Google Workspace Scan</li><li>**11** - Google Workspace</li><li>**12** - IaaS PaaS</li><li>**15** - Salesforce</li><li>**16** - Dynamics 365</li></ul>                 | integer |
| jobModule     | The job module of the job. <ul><li>**0** - None</li><li>**1** - Granular Backup and Restore</li><li>**2** - Exchange Online Backup and Restore</li><li>**3** - Report Center</li><li>**4** - Content Management</li><li>**5** - Deployment</li><li>**6** - Replicator</li><li>**7** - Administrator</li><li>**8** - Archiver</li><li>**9** - Cloud App Admin</li><li>**10** - Retention</li><li>**302** - SharePoint Online</li><li>**303** - Exchange Online</li><li>**304** - Microsoft 365 Groups</li><li>**305** - OneDrive</li><li>**306** - Project Online</li><li>**307** - Exchange Online Public Folders</li><li>**308** - Microsoft Teams</li><li>**309** - Archiver</li><li>**310** - Power BI</li><li>**311** - Power Automate</li><li>**312** - Power Apps</li><li>**355** - Cloud Backup for Azure</li><li>**356** - Azure Virtual Machine</li><li>**357** - Disk</li><li>**358** - Microsoft Entra ID</li><li>**359** - Storage</li><li>**360** - Admin Portal Settings</li><li>**361** - Amazon EC2</li><li>**362** - Azure Sql</li><li>**363** - Dev Ops</li><li>**364** - Microsoft Entra ID B2C</li><li>**365** - Azure Sql Backup</li><li>**366** - Google Virtual machine instance</li><li>**401** - Dynamics</li><li>**402** - Viva Engage</li><li>**501** - Gmail</li><li>**502** - Calendar</li><li>**503** - Contacts</li><li>**504** - Drive</li><li>**505** - Shared Drives</li><li>**506** - Google Classroom</li><li>**507** - Chat</li><li>**508** - Google Directory</li><li>**550** - Dynamic CRMBackup</li><li>**551** - Dynamic AXBackup</li></ul>      | integer |
| status       | The status of the job. <ul><li>**0** - None</li><li>**1** - Running</li><li>**2** - Finished</li><li>**3** - Failed</li><li>**4** - FinishedWithException</li><li>**5** - Skipped</li><li>**6** - Pending</li><li>**7** - ErrorStart</li><li>**8** - Canceled</li><li>**9** - Rejected</li><li>**10** - Stopped</li><li>**11** - NotScan</li><li>**12** - Disabled</li><li>**13** - NotStart</li><li>**14** - WaitForTheConfiguration</li></ul>     | integer |
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
To use this API, send a POST request to the specified endpoint, including necessary parameters as defined in the references.
```json
https://graph.avepointonlineservices.com/partner/external/v3/general/customers/{customerId}/jobs
```
 
## Response Sample
If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.
For more details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).
```json
{
    "data": [
        {
            "jobType": 7,
            "jobModule": 304,
            "status": 3,
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
    ],
    "metadata": {
        "pageIndex": 1,
        "pageSize": 50,
        "totalCount": 2
    }
}
```