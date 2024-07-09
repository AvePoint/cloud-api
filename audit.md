# AOS
## Version: 1.0.0

---
### /audit

#### GET
##### Summary

Gets the audit records for activities within your AvePoint Online Services tenant.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ------ |
| StartTime | query | Specifies the start time for getting the audit records. | No | dateTime |
| EndTime | query | Specifies the end time for getting the audit records. StartTime and EndTime must be no more than 7 days apart. | No | dateTime |
| ProductTypes | query | Specifies the products for which you want to get audit records. Valid values are:     Office365Management: Cloud Management    Office365Backup: Cloud Backup for Microsoft 365    GovernanceAutomation: Cloud Governance    Portal: Confidence Platform Portal    PolicyEnforcer: Policies for Microsoft 365    CPManagement: Insights for Microsoft 365    SMP: EnPower By default, audit records for all products are retrieved. | No | [ string ] |
| GeoLocations | query | Specifies the data center from which to retrieve the audit records. Valid values are:    PrimaryGeoLocation: Central AOS location    NAM: North America    EUR: Europe/Middle East/Africa    GBR: United Kingdom    JPN: Japan    APC: Asia-Pacific    AUS: Australia    CAN: Canada    IND: India    FRA: France    ARE: United Arab Emirates    ZAF: South Africa    CHE: Switzerland    KOR: Korea    DEU: Germany    BRA: Brazil    NOR: Norway    SWE: Sweden    QAT: Qatar    POL: Poland    ITA: Italy By default, audit records for all locations are retrieved. This parameter is only available when the AOS tenant supports Multi-Geo. | No | [ string ] |
| SkipToken | query | When a response contains more data than can be returned in a single call, the API provides a SkipToken in the response. This token can then be passed as a parameter in subsequent requests to retrieve the next set of results. | No | string |

##### Responses

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [ApiQueryWithSkipTokenResultOfUserActivityAuditLogItemModel](#apiquerywithskiptokenresultofuseractivityauditlogitemmodel) |
| 400 |  | [ErrorResponse](#errorresponse) |

---
### Models

#### ApiQueryWithSkipTokenResultOfUserActivityAuditLogItemModel

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| nextLink | string |  | No |
| data | [ [UserActivityAuditLogItemModel](#useractivityauditlogitemmodel) ] |  | No |

#### UserActivityAuditLogItemModel

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| actionName | string | Operation name | No |
| actionUser | string | Operation user | No |
| actionParameters | string | Operation parameters | No |
| actionTime | string | Operation time | No |
| controllerName | string | Operation controller name | No |
| product | string | Product name | No |
| geoLocation | string | Geo location | No |
| previousValue | string | Previous value | No |
| currentValue | string | Current value | No |
| partnerTenantOwner | string | Partner tenant owner | No |
| status | string | Operation status | No |
| comment | string | Operation comment | No |
| objectType | string | Operation object type | No |
| operationType | string | Operation type | No |
| module | string | Operation module | No |
| functionality | string | Operation functionality | No |
| objectName | string | Operation object name | No |
| action | string | Operation name (for Cloud Governance only) | No |
| clientIP | string | IP | No |
| additionalDetails | object | for confide | No |

#### ErrorResponse

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| requestId | string |  | No |
| date | dateTime |  | Yes |
| statusCode | [HttpStatusCode](#httpstatuscode) |  | Yes |

#### HttpStatusCode

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| HttpStatusCode | integer |  |  |
