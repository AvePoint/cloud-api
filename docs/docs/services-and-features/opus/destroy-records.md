# Destroy Records  

Use this API to update the status of records as Destroyed in AvePoint Opus.  
> [!NOTE] 
> You can update the status for up to 15 records at a time; if manual approval is enabled, after record reviewers approve or reject the records, you can use this API to update the status of the approved records as Destroyed in AvePoint Opus. 

## Permission

The following permission is required to call this API.   
You must register an app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API    | Permission  |
|-------------------|---------------------|
| `/records/connector/records` |  records.readwrite.all |

## Request

This section outlines the HTTP method and endpoint used to update the status of records as Destroyed in AvePoint Opus.

| Method | Endpoint | Description |
| --- | --- | --- |
| DELETE | `/records/connector/records` | Updates the status of records as Destroyed in AvePoint Opus. |

## Request Parameters

This section outlines the parameters to specify the records whose status you want to update as Destroyed in AvePoint Opus.  

|Parameter|Description | Type|Required?|
|---|---|---|---|
|disposalIds|The unique key of each record whose status you want to update as Destroyed in AvePoint Opus.|list|Yes|

## Response

The API response provides the outcome of the request.

| Elements   | Description  | Type   | 
|------------|---------------|--------| 
| statusCode      | The request status code.  | integer    | 
| message | The request outcome. | list  | 
| failedItems | If the status of some records failed to be updated to Destroyed in AvePoint Opus, this parameter would appear, displaying the records failed in the request. | list|

## Request Sample

To use this API, send a `DELETE` request to the specified endpoint, including necessary parameters as defined. The following request is an API call to the AvePoint Opus environment in the US - East region.

**URL**

```json
https://graph-us.avepointonlineservices.com/records/connector/records
```
**Body (raw-JSON)** 

```json
{
    "disposalIds" :[ // The unique key of the records whose status you want to update as Destroyed in AvePoint Opus.
        "test_connector_0006",
        "test_connector_0007"
    ]
}
```

## Response Sample

If the request has been successfully processed, a 200 OK response code will be returned.  
For details on the HTTP status code, refer to [HttpStatusCode](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).  

```json
{
    "statusCode": 200, // The request status code.
    "message": null // This message appears when the request has been successfully processed.
}
