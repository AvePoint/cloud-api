# Retrieve Export Job Status

This API method (`/insights/job/{jobId}/exportstatus` navigation property) allows users to retrieve the status of an export job. This method is useful for monitoring the progress and completion status of export jobs.

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/job/{jobId}/exportstatus` |  insights.graph.readwrite.all |

## Request

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant job status details in a structured format, enabling easy integration with other systems or applications.

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/job/{jobId}/exportstatus` | Retrieves the job status of an export job. |

## Query Parameters

The API supports a single query parameter to specify the job ID for which the status is being requested.

| Parameter | Description | Type    | Required? |
|-----------|-------------|---------|-----------|
| jobId     | Job ID     | integer | Yes       |

## Responses

The API response provides detailed information about the job status. 

| Elements   | Description                | Type    |
|------------|----------------------------|---------|
| jobStatus  | The status of the job. **1** for In progress; **2** for Finished; **3** for Failed.      | enum |
| status     | The HTTP response status code | integer |
| message    | The error message          | string  |

## Request Sample

To use this API, send a `GET` request to the specified endpoint, including the job ID as defined. The following request is an API call to the Insights for Microsoft 365 environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/insights/job/169/exportstatus
```

## Response Sample

This API response returns the job status.

```json
{
  "jobStatus": 2,    //job status. 2 for finished in this case.
  "status":200,    //operation status
  "message": ""    //error message
}