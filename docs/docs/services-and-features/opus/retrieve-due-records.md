# Retrieve Due Records  

Use this API to retrieve the records whose disposal due date is earlier than the specified time.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API    | Permission  |
|-------------------|---------------------|
| `/records/connector/records` |  records.readwrite.all |

## Request

This section outlines the HTTP method and endpoint used to retrieve records whose disposal due date is earlier than the specified time.  

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/records/connector/records` | Retrieves records whose disposal due date is earlier than the specified time. |

## Request Parameters

The API requires multiple parameters to retrieve records whose disposal due date is earlier than the specified time.  

|Parameter|Description| Type|Required?|
|---|---|---|---|
|id|The ID of the connection. You can find it from the JSON file.|GUID|Yes|
|disposalDueDate|The disposal due date.|string|Yes|
|startIndex|The page index of the last request.|string|No|
|itemsPerPage|The number of records that you want to request per page. The valid value is a number between 0 and 100.|integer|Yes|

## Response

The API response provides the outcome of the request.

| Parameter |Description |Type | 
|-----------|-------------|-----|
| message     | The request outcome.      | string    | 
| startIndex |The page index of the records that are queried in the request. | string  |
| queriedItems  |The records that match the request information. | list  | 

**Record Details**

Each record retrieved through the API includes detailed attributes. 

| Parameter   |Description        | Type   | 
|--------------------|---------------------|--------|
|rowKey|The unique key of the record.|string|Yes|
|leafName|The name of the record.|string|Yes|
|termFullPath|The classification (term full path) of the record.|string|No|
|timeCreated| The created time of the record.|string |Yes|  
|timeModified|The modified time of the record.|string|Yes|
|createdBy|The creator of the record.|string|Yes|
|modifiedBy|The modifier of the record.|string|Yes|

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined. The following request is an API call to the AvePoint Opus environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/records/connector/records?id=63acafab-b2b8-4b44-8ddb-7a47672c2393&disposalDueDate=2024-12-20T11:13:00&startIndex=&itemsPerpage=10
```

## Response Sample

If the quest has been successfully processed, a 200 OK response code will be returned.  
For details on the HTTP status code, refer to [Http Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).  

```json
{
    "startIndex": null, // The page index of the records that are queried in the request.
    "statusCode": 200, // The request status code.
    "queriedItems": [ // The detailed information of each queried record.
        {
            "rowKey": "test_connector_0006", // The unique key of the record.
            "leafName": "test_connector_record6", // The name of the record.
            "termFullPath": "Connector/Connector-termset/Connector-term", //The classification (term full path) of the record.
            "timeCreated": "2024-12-19 18:15:00 ", //The created time of the record.
            "timeModified": "2024-12-19 18:15:00 ", //The modified time of the record.
            "createdBy": "jack.smith", //The creator of the record.
            "modifiedBy": "jack.smith" //The modifier of the record.
        },
    ]
}
