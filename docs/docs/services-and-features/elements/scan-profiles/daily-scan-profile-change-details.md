# Elements API

Elements provides APIs to retrieve information of your customers, including services, job details, and scan profiles.

## Permissions  

The following permission is required to call the APIs.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](/docs/docs/Use%20AvePoint%20Graph%20Modern%20API.md/#authentication-and-authorization)

| API |Method| Description | Permission Required |
|-----------|--------|-------|--------|
| [/Customers/{id}/ScanProfilesDailyNewDetail/ProfileId/{ProfileId}](#getcustomersidscanprofilesdailynewdetailprofileidprofileid) | GET |Get your customer's daily scan profile change details in AvePoint Online Services.  | partner.scanprofiles.read.all|  

## References


### [GET]/Customers/{id}/ScanProfilesDailyNewDetail/ProfileId/{ProfileId}

Get your customer's daily scan profile change details in AvePoint Online Services.

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
| LastUpdateTime | The time the daily report for the scan profile was generated. If no daily report has been generated, the time will be the last modified time of the scan profile. | String |
| NewRegisteredContent | The details of newly registered objects in the daily report of the scan profile. | String |
| RemovedFromMicrosoft365OrOutOfPolicyObjects | The details of objects moved to another container in the daily report of the scan profile. | String |
| MovedToAnotherContainerObjects | The details of objects removed from Microsoft 365 or out of policy in the daily report of the scan profile. | String |




