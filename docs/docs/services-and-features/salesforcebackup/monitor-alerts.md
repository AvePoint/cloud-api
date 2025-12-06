# Retrieve Alert Records

Get the basic information of alert records (`/backup/sfbapi/monitor-alerts` navigation property) of Cloud Backup for Salesforce®. By invoking the `/backup/sfbapi/monitor-alerts` endpoint, users can proactively maintain integrity, and respond quickly to issues.  

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API   | Permission  |
|-------------------|----------------------|
|`/backup/sfbapi/monitor-alerts`| salesforce.public.read.all |

## Request

This section outlines the HTTP method and endpoint used to retrieve the basic information of alert records. It provides a concise description of the action performed by the API call.

| Method | Path | Description |
| --- | --- | --- |
| GET | `/backup/sfbapi/monitor-alerts` | Gets the data alerts information of Cloud Backup for Salesforce®. |

## Query Parameters

The API supports a query parameter to refine and customize the data retrieval process. This parameter allow uses to specify the time ranges, and other criteria to filter the results effectively.  

| Parameter | Description | Type | Required? |
| --- | --- | --- | --- |
| startTime | Sets a start time (UTC time) for the time range in ISO 8601 format. For example, 2024-01-01.| string | Yes |
| finishTime | Sets an end time (UTC time) for the time range in ISO 8601 format. For example, 2024-12-01.| string | Yes |
| organizationId | Sets the source organization that you want to get. | string | No |
| alertType | Chooses between Data and Metadata alerts. | enum | No |

## Responses

The API provides detailed information about data alert records retrieved. It includes data on organization ID, object, operation and record number.

**Retrieved result:**

| Elements | Description | Type |
| --- | --- | --- |
| statusCode | Http Response Status Code | integer |
| message | Error message | string |
| errors | API error | ApiError |
| data | Alert Records | AlertDataResult |
| requestId | API Request ID | string |
| timestamp | API request time | string |
| traceId | API Trace ID | string |

**AlertDataResult:**

| Elements | Description | Type |
| --- | --- | --- |
| organizationId | The ID of the organization with changes. | string |
| objectType | The object type that has been changed. | integer |
| operation | The operation type that the object has been changed.<br> Valid values: <br> <ul><li>**0** for Added <br> </li><li>**1** for Modified <br> </li><li>**2** for Removed <br> </li></ul> | integer |
| recordNumber | Number of records that have been affected. | long |
| collectTime | The time when we detect alert information. | string |

## Request Sample

To use this API, send a GET request to the specified endpoint. This will return the basic information of alert records in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the Cloud Backup for Salesforce® environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/backup/sfbapi/monitor-alerts?startTime=2024-10-24&finishTime=2024-12-25
```

## Response Sample

If successful, this method returns a 200 OK response code and the basic information of alert records in the response body.  
For details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
    "statusCode": 200, //Http Response Status Code
    "message": "", //Error message
    "data": [
        {
            "organizationId": "00Dam00000kxWaGEAU", //The ID of the organization changes
            "objectType": "classes", //The object type that has been changed
            "operation": 0, //The operation type that the object has been changed
            "recordNumber": 1046, //Number of records that have been affected
            "collectTime": "2025-10-20T08:30:00Z" //The time when we detect alert information
        },
        {
            "organizationId":"00Dam00000kxWaGEAU", //The ID of the organization changes
            "objectType": "content Versions", //The object type that has been changed
            "operation":0, //The operation type that the object has been changed
            "recordNumber": 6276, //Number of records that have been affected
            "collectTime": "2025-10-20T08:30:00Z" //The time when we detect alert information
        },
        {
            "organizationId":"00Dam00000kxWaGEAU", //The ID of the organization changes
            "objectType": "email", //The object type that has been changed
            "operation":2, //The operation type that the object has been changed
            "recordNumber": 1046, //Number of records that have been affected
            "collectTime": "2025-10-20T08:30:00Z" //The time when we detect alert information
        }
    ],
    "requestId": "0HNEVHLNSPSEJ:00000003", //API Request ID
    "timestamp": "2025-08-20T03:36:54.780972Z",  //API request time
    "traceId": "00-7d7a9360e98bd75eaee0a0ae652adf1d-efcd6c0533a5225d-00" //API Trace ID
}