# AvePoint Online Services

## Permissions

The following table indicates the permissions required by API operations.

| API operation    | Permission required | Permission type |
|-------------------|---------------|----------------------|
| [GET](#get) audit records | audit.read.all           | Application       |
-------------------------------------------

## GET

Gets the audit records for activities in your AvePoint Online Services tenant within a time range.

### Optional query parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ------ |
| StartTime | query | Sets a start time for the time range. | No | dateTime |
| EndTime | query | Sets an end time for the time range. The time range between StartTime and EndTime must be no more than 7 days. | No | dateTime |
| ProductTypes | query | If no value is set for this parameter, this method retrieves the audit records for all products in your AOS tenant. To get audit records from specific products, use the following values:     <ul><li>**Office365Management** (Cloud Management)</li> <li>**Office365Backup** (Cloud Backup for Microsoft 365)</li> <li>**GovernanceAutomation** (Cloud Governance)</li> <li>**Portal** (AvePoint Online Services)</li> <li>**PolicyEnforcer** (Policies for Microsoft 365)</li> <li>**CPManagement** (Insights for Microsoft 365)</li> <li>**SMP** (EnPower)</li></ul> | No |  string  |
| GeoLocations | query | This parameter is only available for the AOS tenant that supports Multi-Geo. If no value is set for this parameter, this method retrieves the audit records from all locations in your AOS tenant. To get audit records from specific data centers, use the following values: <ul><li>**PrimaryGeoLocation** (Central AOS location)</li> <li>**NAM** (North America)</li> <li>**EUR** (Europe/Middle East/Africa)</li> <li>**GBR** (United Kingdom)</li> <li>**JPN** (Japan)</li> <li>**APC** (Asia-Pacific)</li> <li>**AUS** (Australia)</li> <li>**CAN** (Canada)</li> <li>**IND** (India)</li> <li>**FRA** (France)</li>    <li>**ARE** (United Arab Emirates)</li> <li>**ZAF** (South Africa)</li> <li>**CHE** (Switzerland)</li> <li>**KOR** (Korea)</li> <li>**DEU** (Germany)</li> <li>**BRA** (Brazil)</li> <li>**NOR** (Norway)</li> <li>**SWE** (Sweden)</li> <li>**QAT** (Qatar)</li> <li>**POL** (Poland)</li> <li>**ITA** (Italy)</li></ul>  | No |  string  |
| SkipToken | query | During a query, if the results are too large to be returned in a single response, a **SkipToken** is included in the response. This token allows you to retrieve the next set of results by appending it into the query URL in a subsequent request. | No | string |

### Responses

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | If successful, the method returns this code. | [ApiQueryWithSkipTokenResultOfUserActivityAuditLogItemModel](#apiquerywithskiptokenresultofuseractivityauditlogitemmodel) |
| 400 | If an error occurs, the method returns this code. | [ErrorResponse](#errorresponse) |

### Models

The following sections describe the response models to get audit records.

#### ApiQueryWithSkipTokenResultOfUserActivityAuditLogItemModel

Response model to get audit records successfully.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| nextLink | string |  | No |
| data | [UserActivityAuditLogItemModel](#useractivityauditlogitemmodel)  |  | No |

#### UserActivityAuditLogItemModel

If successful, the following objects are displayed in the response body.

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
| additionalDetails | object | Operation name (for Confide only) | No |

#### ErrorResponse

If an error occurs, the following information is displayed in the response body.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| requestId | string | Represents the request ID. | No |
| date | dateTime |Represents the date and time of this request  | Yes |
| statusCode | [HttpStatusCode](#httpstatuscode) |Represents the HTTP error code.  | Yes |

#### HttpStatusCode

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| HttpStatusCode | integer |  |  |

[description is missing here]: #