# Retrieve Unusual Activities

Get the basic information of unusual activities (`/backup/sfbapi/unusual-activities` navigation property) detected by Cloud Backup for Salesforce®. By invoking the `/backup/sfbapi/unusual-activities` endpoint, users can gain the number of sites with unusual activities and that are under potential ransomware attacks in your tenant.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission |
|---|---|
|`/backup/sfbapi/unusual-activities` | salesforce.public.read.all |

## Request

This section outlines the HTTP method and endpoint used to retrieve the basic information of unusual activities. It provides a concise description of the action performed by the API call.  

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/backup/sfbapi/unusual-activities` | Gets the basic information of unusual activities detected by Cloud Backup for Salesforce. |

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow uses to specify the detected time range and organizationId to filter the results effectively.  

| Parameter  | Description | Type   | Required? |
|------------|-------------|--------|-----------|
| startTime  | Sets a start time (UTC time) for the detected time range. For example, 2024-01-01.| string | Yes |
| finishTime | Sets a end time (UTC time) for the detected time range. For example, 2024-12-01. | string | Yes |
| organizationId | Sets the source organization that you want to get. | string | No |

## Responses

The API response provides the basic information of unusual activities. Each job in the response includes various attributes that describe its properties and status.

**Retrieved result:**

| Elements | Description | Type |
| --- | --- | --- |
| statusCode | Http Response Status Code | integer |
| message | error message | string |
| errors | API error | ApiError |
| data | Basic information of unusual activities | unusualactivitydata |
| requestId | API Request ID | string |
| timestamp | API request time | string |
| traceId | API Trace ID | string |

**Basic information of unusual activities**

| Elements | Description | Type   |
| --- | --- | --- |
| organizationId | The ID of the organization with unusual activities. | string |
| organizationName | The name of the organization with unusual activities. | string |
| latestDetectedDate | The last detected date for unusual activities. | string |
| suspiciousFiles  | Number of suspicious files. | long |
| addedFiles  | Number of files added. | long |
| modifiedFiles | Number of files modified. | long |
| deletedFiles | Number of files deleted. | long |

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. This will return the basic information of unusual activities in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the Cloud Backup for Salesforce® environment in the US - East region.  

```json
https://graph-us.avepointonlineservices.com/backup/sfbapi/unusual-activities?StartTime=2024-01-01&FinishTime=2024-12-30
```

## Response Sample

If successful, this method returns a 200 OK response code and the basic information of unusual activities in the response body.  
For details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "statusCode": 200, //Http Response Status Code
    "message": "", //Error message
        "data": [
          {
              "organizationId":"00Dam00000kxWaGEAU", //The ID of the organization with unusual activities 
              "organizationName":"AvePoint Production", //The name of the organization with unusual activities
              "latestDetectedDate":"2025-10-01T00:00:00Z", //The last detected date for unusual activities
              "suspiciousFiles":0, //Number of suspicious files
              "addedFiles": 2, //Number of files added
              "modifiedFiles": 3, //Number of files modified
              "deletedFiles":0 //Number of files deleted
          }
        ],
    "requestId": "0HNEVHLNSPSEJ:00000004", //API Request ID
    "timestamp": "2025-08-20T03:45:46.3561083Z",  //API request time
    "traceId": "00-670aa1d01485c1a7bbcc88bd48b05ed7-ecfba726763bda2a-00" //API Trace ID
}
