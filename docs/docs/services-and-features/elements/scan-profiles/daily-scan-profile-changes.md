# Elements API

Elements provides APIs to retrieve information of your customers, including services, job details, and scan profiles.

## Permissions  

The following permission is required to call the APIs.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](/docs/docs/Use%20AvePoint%20Graph%20Modern%20API.md/#authentication-and-authorization)

| API |Method| Description | Permission Required |
|-----------|--------|-------|--------|
| [/Customers/{id}/ScanProfilesDailyNew/ProfileId/{ProfileId}](#getcustomersidscanprofilesdailynewprofileidprofileid) | GET |Get your customer's daily scan profile changes in AvePoint Online Services.| partner.scanprofiles.read.all |  

## References


### [GET]/Customers/{id}/ScanProfilesDailyNew/ProfileId/{ProfileId}

Get your customer's daily scan profile changes in AvePoint Online Services.

#### Parameters (Query)

| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |
| ProfileId | The ID of the scan profile. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| ProfileName | The name of the scan profile. | String |
| ProfileId | The ID of the scan profile. | String |
| TenantDomain | The tenant domain of the scan profile. | String |
| TenantId | The tenant ID the scan profile. | String |
| Description | The description of the scan profile. | String |
| ScanMode | The scan mode of the scan profile:<br> <ul><li>**0** represents **Express mode**<li>**1** represents **Advanced mode**| Int |
| ModifiedTime | The last modified time of the scan profile. | String |
| LastUpdateTime | The time the daily report for the scan profile was generated. If no daily report has been generated, the time will be the last modified time of the scan profile. | String |
| LastScanStatus | The last scan job status of the scan profile:<br><ul><li>**2** represents **Finished**<li>**3** represents **Failed**<li>**4** represents **Finished with exception**<li>**5** represents **Skipped**<li>**10** represents **Stopped** | Int |
| NewRegisteredContentCount | The number of newly registered objects in the daily report of the scan profile. | Int |
| MovedToAnotherContainer | The number of objects moved to another container in the daily report of the scan profile. | Int |
| RemovedFromMicrosoft365OrOutofPolicy | The number of objects removed from Microsoft 365 or out of policy in the daily report of the scan profile. | Int |

***
