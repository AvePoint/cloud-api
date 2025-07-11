# Retrieve Audit Records

Use this API to retrieve audit records (`/aos/audit` navigation property) for activities within your AOS tenant. This article outlines the necessary permissions, available methods, and models used for interacting with the API.  

## Permission

The following permission is required to call this API.  

You must register an app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API    | Permission  | 
|-------------------|---------------------|
| `/aos/audit` | audit.read.all |

## Request

This section outlines the HTTP method and endpoint that is used to retrieve the audit records. 

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/aos/audit` | Retrieves user activities in your AvePoint Online Services tenant within a time range. |

## Query Parameters

The API supports the following query parameters to refine and customize the data retrieval process. These parameters allow users to specify time ranges, product types, geo locations and other criteria to filter the results effectively.

| Parameter | Description |  Type |Required |
| ---- | ---------------- | -------- | ------ |
| startTime |  Sets a start time for the time range in ISO 8601 format. |  string |No |
| endTime |  Sets an end time for the time range in ISO 8601 format. The time range between StartTime and EndTime must be no more than 7 days.  | string |No |
| productTypes | If no value is set for this parameter, this method retrieves the audit records for all products in your AOS tenant. To get audit records from specific products, use the following values:     <ul><li>**Office365Management** (Cloud Management)</li> <li>**Office365Backup** (Cloud Backup for Microsoft 365)</li> <li>**GovernanceAutomation** (Cloud Governance)</li> <li>**Portal** (AvePoint Online Services)</li> <li>**PolicyEnforcer** (Policies for Microsoft 365)</li> <li>**CPManagement** (Insights for Microsoft 365)</li> <li>**SMP** (EnPower)</li> <li>**VDR** (Confide)</li> <li>**AvePointRecords** (Opus)</li> <li>**GsuiteBackup** (Cloud Backup for Google Workspace)</li></ul> | string  |No |  
| geoLocations |  This parameter is only available for AOS tenants that support Multi-Geo. If no value is set for this parameter, this method retrieves the audit records from all locations in your AOS tenant. To get audit records from specific data centers, use the following values: <ul><li>**PrimaryGeoLocation** (Central AOS location)</li> <li>**NAM** (North America)</li> <li>**EUR** (Europe/Middle East/Africa)</li> <li>**GBR** (United Kingdom)</li> <li>**JPN** (Japan)</li> <li>**APC** (Asia-Pacific)</li> <li>**AUS** (Australia)</li> <li>**CAN** (Canada)</li> <li>**IND** (India)</li> <li>**FRA** (France)</li>    <li>**ARE** (United Arab Emirates)</li> <li>**ZAF** (South Africa)</li> <li>**CHE** (Switzerland)</li> <li>**KOR** (Korea)</li> <li>**DEU** (Germany)</li> <li>**BRA** (Brazil)</li> <li>**NOR** (Norway)</li> <li>**SWE** (Sweden)</li> <li>**QAT** (Qatar)</li> <li>**POL** (Poland)</li> <li>**ITA** (Italy)</li></ul>  | string  |No |  
| skipToken |  During a query, if the results are too large to be returned in a single response, a **skipToken** is included in the response. This token allows you to retrieve the next set of results by appending it into the query URL in a subsequent request. |string | No | 

## Response

The API response provides detailed information about the audit records retrieved. 

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | If successful, the method returns this code. | [ApiResultOfUserActivityModel](#apiresultofuseractivitymodel) |
| 400 | If an error occurs, the method returns this code. | [ErrorResponse](#errorresponse) |

### Response Models

The following sections describe the response models to get audit records.

#### ApiResultOfUserActivityModel

This model is returned upon successful retrieval of audit records.

| Name |  Description | Type |Required |
| ---- | ---- | ----------- | -------- |
| nextLink |  If multiple query requests are required to retrieve all the results, the response returns the **nextLink** property, and the **nextLink** value is a URL to the next page of results. You can retrieve the next page of results by sending the URL value of the **nextLink** property. |string | No |
| data |  The query parameters in the response of getting audit records. | [UserActivityAuditLogItemModel](#useractivityauditlogitemmodel)  |No |

#### UserActivityAuditLogItemModel

If successful, the following objects are displayed in the response body.

| Name |  Description | Type |Required |
| ---- | ---- | ----------- | -------- |
| actionName |  Name of the action.|string  | No |
| actionUser |  User of the action. |string | No |
| actionParameters | Parameters in the action. | string | No |
| actionTime |  Time of the action in ISO 8601 format. |string | No |
| controllerName |  Controller in the action. | string |No |
| product |  Name of product. Valid values:     <ul><li>**Cloud Management**</li> <li>**Cloud Backup for Microsoft 365**</li> <li>**Cloud Governance**</li> <li>**AvePoint Online Services**</li> <li>**Policies for Microsoft 365**</li> <li>**Insights for Microsoft 365**</li> <li>**EnPower**</li> <li>**Confide**</li> <li>**Opus**</li> <li>**Cloud Backup for Google Workspace**</li></ul> | string |No |
| geoLocation |  Geo locations of a multi-geo tenant. | string |No |
| previousValue |  Previous value of the action. | string |No |
| currentValue |  Current value of the action. | string |No |
| partnerTenantOwner |  Tenant owner of the service provider managing the customer's AOS tenant. | string |No |
| status |  Status of the action. |string | No |
| comment | Comment for the action. | string | No |
| objectType |  Type of the action object. |string | No |
| operationType | Type of the action. |string |  No |
| module |  Module of the action. | string |No |
| functionality | Functionality related to the action. |  string |No |
| objectName | Name of the object related to the action. | string | No |
| action |  Name of the action. This parameter is only for Cloud Governance. |string | No |
| clientIP |  Public IP address for the action. |string | No |
| additionalDetails |  Name of the action. This parameter is only for Confide. |object | No |

#### ErrorResponse

If an error occurs, the following information is displayed in the response body.

| Name |  Description | Type |
| ---- | ---- | ----------- | 
| traceId | The unique identifier used to trace and track the flow of a request. | string |
| error | The error message.   |string |
| statusCode | The HTTP error code.  | [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code) |

## Request Sample

The following request is an API call to the AvePoint Online Services (AOS) environment in the US - East region. The API method being used is `/aos/audit`. This request is designed to fetch a specific set of audit logs from the AOS portal, within a defined timeframe, and limited to a particular geographical location.

```json
https://graph-us.avepointonlineservices.com/aos/audit?startTime=2024-10-10T08:00:00Z&endTime=2024-10-14T17:00:00Z&productTypes=Portal&geoLocations=NAM
```

## Response Sample

If successful, this method returns a 200 OK response code and a collection of user activities in the response body.

```json
{
    "nextLink": null, // No results in the next page
    "data": [
        {
            "actionName": "Session Timeout", // Name of the action
            "actionUser": "dev@test.onmicrosoft.com", // User of the action
            "actionParameters": "null", // No parameters in the action
            "actionTime": "2024-10-14T07:41:50Z", // Time of the action
            "controllerName": "AccountController", // No controller in the action
            "product": "AvePoint Online Services", // Name of product
            "geoLocation": null, // Not a multi-geo tenant
            "previousValue": null, // No previous value of the action
            "currentValue": null, // No current value of the action
            "partnerTenantOwner": null, // Not a customer managed by service providers
            "status": null, // Status of the action
            "comment": null, // No comment for the action
            "objectType": null, // Type of the action object
            "operationType": null, // No action type
            "module": null, // Module of the action
            "functionality": null, // No functionality related to the action
            "objectName": null, // No object related to the action
            "action": null, // Parameter for Cloud Governance only
            "clientIP": "123.123.12.123", // Public IP address for the action
            "additionalDetails": {} // Parameter for Confide only
        }
    ]
}
