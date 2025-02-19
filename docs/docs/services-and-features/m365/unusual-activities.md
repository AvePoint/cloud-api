# Retrieve Unusual Activities

Get the basic information of unusual activities (`/backup/m365/unusualactivitydata` navigation property) detected by Cloud Backup for Microsoft 365. By invoking the `/backup/m365/unusualactivitydata` endpoint, users can gain the number of sites with unusual activities and that are under potential ransomware attacks in your tenant.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API   | Permission |
|---|---|
|`/backup/m365/unusualactivitydata` | microsoft365backup.unusualActivity.read.all|

## Request

This section outlines the HTTP method and endpoint used to retrieve the basic information of unusual activities. It provides a concise description of the action performed by the API call.  

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/backup/m365/unusualactivitydata` | Gets the basic information of unusual activities detected by Cloud Backup for Microsoft 365. |

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow uses to specify the detected time range and location to filter the results effectively.  


| Parameter  | Description | Type   | Required? |
|------------|-------------|--------|-----------|
| startTime  | Sets a start time (UTC time) for the detected time range. For example, 2024-01-01.| string | Yes |
| finishTime    | Sets a end time (UTC time) for the detected time range. For example, 2024-12-01. | string | Yes |
| location   | This parameter is only available for AOS tenants that support Multi-Geo. If no value is set for this parameter, this method retrieves the unusual activities from all locations in your AOS tenant. To get unusual activities from specific data centers, use the following values: <ul><li>**PrimaryGeoLocation** (Central AOS location)</li> <li>**NAM** (North America)</li> <li>**EUR** (Europe/Middle East/Africa)</li> <li>**GBR** (United Kingdom)</li> <li>**JPN** (Japan)</li> <li>**APC** (Asia-Pacific)</li> <li>**AUS** (Australia)</li> <li>**CAN** (Canada)</li> <li>**IND** (India)</li> <li>**FRA** (France)</li>    <li>**ARE** (United Arab Emirates)</li> <li>**ZAF** (South Africa)</li> <li>**CHE** (Switzerland)</li> <li>**KOR** (Korea)</li> <li>**DEU** (Germany)</li> <li>**BRA** (Brazil)</li> <li>**NOR** (Norway)</li> <li>**SWE** (Sweden)</li> <li>**QAT** (Qatar)</li> <li>**POL** (Poland)</li> <li>**ITA** (Italy)</li></ul>     | string | No |

## Responses

The API response provides the basic information of unusual activities. Each job in the response includes various attributes that describe its properties and status.

| Elements | Description | Type   |
| --- | --- | --- |
| tenantOwner | Tenant owner | string |
| tenantId | Tenant ID | string |
| serviceType | Type of service <br> Valid values: <br> <ul><li> **0** for Exchange Online <br> </li><li>**1** for  SharePoint Online <br> </li><li>**2** for OneDrive <br> </li><li>**3** for Microsoft 365 Groups <br> </li><li>**4** for Project Online <br> </li><li>**5** for Public Folder <br> </li><li>**6** for Teams <br> </li><li>**7** for Public Folder Metadata <br> </li><li>**8** for Private Channel <br> </li><li> **9** for Yammer Group <br> </li><li>**10** for Personal Chat <br> </li><li>**11** for Power BI <br> </li><li>**12** for Power Automate <br> </li><li>**13** for Shared Channel <br> </li><li>**14** for Power Apps</li></ul> | integer |
| potentialRansomwareAttackCount  | Number of sites with unusual activities | long |
| unusualActivitiesCount | Number of sites under potential ransomware attacks | long |

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. This will return the basic information of unusual activities in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the Cloud Backup for Microsoft 365 environment in the US - East region.  

```json
https://graph-us.avepointonlineservices.com/backup/m365/unusualactivitydata?StartTime=2024-01-01&FinishTime=2024-12-30?Location=NAM
```

## Response Sample

If successful, this method returns a 200 OK response code and the basic information of unusual activities in the response body.  
For details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).

```json
{
  "data": [
    {
      "tenantOwner": "John Doe", //Tenant owner
      "tenantId": "12345678-1234-1234-1234-123456789012", //Tenant ID
      "serviceType": 1, //Service type
      "potentialRansomwareAttackCount": 5, //Number of sites with unusual activities
      "unusualActivitiesCount": 10, //Number of sites under potential ransomware attacks
    }
  ]
}
```