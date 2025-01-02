# Submit Records  

Use this API to submit records to AvePoint Opus. Prepare the information of records based on the JSON file of the connection you have downloaded from the AvePoint Opus > **Settings > Connector** page.

***Note**: You can submit up to 15 records to AvePoint Opus at a time.  

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph Modern API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API    | Permission  |
|-------------------|---------------------|
| `/connector/records` |  records.readwrite.all |

## Request

This section outlines the HTTP method and endpoint used to submit records to AvePoint Opus.  

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/connector/records` | Submits records to AvePoint Opus. |

## Request Parameters

The API requires multiple parameters to submit records to AvePoint Opus.  

|Parameter|Description | Type|Required?|
|---|---|---|---|
|id|The ID of the connection. You can find it from the JSON file. |GUID|Yes|
|conflictOption|The conflict resolution when submitting records to AvePoint Opus if there is a conflict with the unique key of the record.<ul><li> **Overwrite** to overwrite the record information in AvePoint Opus.</li><li> **Skip** to skip submitting the record to AvePoint Opus. </li></ul>|string|Yes|
|rowKey|The unique key of the record.|string|Yes|
|leafName|The internal name of the built-in **Name** column of the connection. You can find it from the JSON file.|string|Yes|
|termFullPath|The internal name of the built-in **Classification**  column of the connection. You can find it from the JSON file. The value must be the full path of a term in AvePoint Opus.|string|No|
|timeCreated| The internal name of the built-in **Created time** column of the connection. You can find it from the JSON file.|string |Yes|  
|timeModified|The internal name of the built-in **Modified Time** column of the connection. You can find it from the JSON file.|string|Yes|
|createdBy|The internal name of the built-in **Created By** column of the connection. You can find it from the JSON file.|string|Yes|
|modifiedBy|The internal name of the built-in **Modified By** column of the connection. You can find it from the JSON file.|string|Yes|

***Note**: For the **Choice (single selection)** type of column, the value must be the option order, instead of the option name. For the **Choice (multiple selections)** type of column, the value must be the option orders separated with a comma in square brackets. For the **Person or Group** type of column, the value must be the full email address of users and/or groups separated with a comma in square brackets. If the user or email does not exist in AvePoint Opus, AvePoint Opus will query the user or group in the Microsoft Entra that is authorized via the app profile in AvePoint Online Services.

## Response

The API response provides the outcome of the request. 

| Parameter           | Description                                                           | Type   | 
|--------------------|-----------------------------------------------------------------------|--------| 
| statusCode      | The request status code.                 | integer    | 
| message             | The request outcome.              | string  | 
| failedItems     | If some records failed to be submitted to AvePoint Opus, this parameter would appear, displaying the records failed in the request. | Arrary|

## Request Sample

To use this API, send a POST request to the specified endpoint, including necessary parameters. 

```json
https://graph-us.avepointonlineservices.com/records/connector/records
```
```json
{  
    "id": " ", // The ID of the connection.
      "confilictOption": "Overwrite", // The conflict resolution when submitting records to AvePoint Opus if there is a conflict with the unique key of the record. Overwrite is to overwrite the record information in AvePoint Opus.
      "data": [
          {
          "rowKey": "SingleText", // The unqiue key of the record.
          "leafName": "SingleText", // The internal name of the built-in Name column of the connection.
          "termFullPath": "Taxonomy", // The internal name of the built-in Classification column of the connection. The value must be the full path of a term in AvePoint Opus.
          "timeCreated": "DateTime", // The internal name of the built-in Created time column of the connection. 
          "timeModified": "DateTime", // The internal name of the built-in Modified time column of the connection.
          "createdBy": "SingleText", // The internal name of the built-in Created by column of the connection.
          "modifiedBy": "SingleText", // The internal name of the built-in Modified by column of the connection.
          }
      ]
 }
```

## Response Sample

If the request has been successfully processed, a 201 response code will be returned.</br>
For details on the HTTP status code, refer to [HTTP Status Code](/docs/Use%20AvePoint%20Graph%20Modern%20API.md/#http-status-code).  

```json
{
    "statusCode": 201, // The request status code.
    "message": null // This message appears when the request has been successfully processed.
}
```

<!-- ### Responses

If successful, this method returns a 200 OK response code and a collection of  jobs in the response body.

## References

### #/components/schemas/Dynamics365.Enums.BackupRestoreType

The `BackupRestoreType` component is an enumeration used to define different types of backup and restore options within Cloud Backup for Dynamics 365. It employs an integer type for representation.  

```ts
{
  "enum": [
    0,
    1,
    2,
    4,
    8,
    16
  ],
  "type": "integer",
  "format": "int32"
}
```

### #/components/schemas/Dynamics365.Model.PageModel

The `PageModel` component specifies pagination details used within Cloud Backup for Dynamics 365 models. It helps manage how data is presented in a paginated format.  

```ts
{
  //Indicates the current page number.
  currentPage?: integer
  //Indicates the number of items per page.
  pageSize?: integer
}
```

### #/components/schemas/Dynamics365.Model.Request.JobFilterModel

The `JobFilterModel` is a request schema designated for filtering job-related data from Cloud Backup for Dynamics 365. It allows users to set various criteria to refine their search and retrieval of job information.  

```ts
{
  //Contains pagination details with `currentPage` and `pageSize`.
  pageInfo: {
    currentPage?: integer
    pageSize?: integer
  }
  //Specifies the job type.
  type?: enum[0, 1, 2, 4, 8, 16]
  //Specifies the start time and end time for the time range.
  startTime?: string
  endTime?: string
  //Specifies the job status.
  status?: integer
  //Specifies organization ID for filtering by organizations.
  organizationId?: string
  //Specifies the object type.
  objectType?: integer
}
``` -->
