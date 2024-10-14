# Elements API

Elements provides APIs to retrieve information of your customers, including services, job details, and scan profiles.

## Permissions  

The following permission is required to call the APIs.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](/docs/docs/Use%20AvePoint%20Graph%20Modern%20API.md/#authentication-and-authorization)

| API |Method| Description | Permission Required |
|-----------|--------|-------|--------|
| [/Customers/{id}/ScanProfiles](#getcustomersidscanprofiles) | GET | Get your customer's information for all scan profiles configured in AvePoint Online Services. | partner.scanprofiles.read.all |  


## References

### [GET]/Customers/{id}/ScanProfiles

Get your customer's information for all scan profiles configured in AvePoint Online Services.

#### Parameters (Query)
| Parameter | Description | Type |
| --- | --- | --- |
| Id | The tenant owner ID of the customer. | String |

#### Responses

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

| Response | Description | Type |
| --- | --- | --- |
| ProfileName | The name of the scan profile. | String |
| ProfileId | The ID of the scan profile. | String |
| ScanMode | The scan mode of the scan profile:<br> <ul><li> **0** represents **Express mode**</li><li> **1** represents **Advanced mode** | Int |
| ModifiedTime | The last modified time of the scan profile. | String |

