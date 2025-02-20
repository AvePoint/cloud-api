# Retrieve Job Information  

Use this API to retrieve the job-related information (`/backup/google/admin/jobs` navigation property) from Cloud Backup for Google Workspace. By invoking the `/backup/google/admin/jobs` endpoint, Users can obtain in-depth insights and data on specific job reports, improving their capability to effectively manage and analyze job information.  

## Permission

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API    | Permission  |
|-------------------|---------------------|
| `/backup/google/admin/jobs` | gsuite.graph.read.all |

## Request

This section outlines the HTTP method and endpoint used to retrieve job information. It provides a concise description of the action performed by the API call.  

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/backup/google/admin/jobs` | Retrieves comprehensive job information. |

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify pagination, job types, time ranges, and other criteria to filter the results effectively.  

|Parameter|Description | Type|Required?|
|---|---|---|---|
|dataSource|Sets the data source for the job that you want to get. The default value is 1. <br> Valid values:<br> <ul><li> **1** for Admin</li><li> **2** for ReCenter </li></ul>|enum  |No|
|appType|Sets the service types of the jobs to get.<br> Valid values:<br> <ul><li> **1** for Gmail</li><li> **2** for Drive </li><li> **4** for Calendar </li><li>**8** for Contacts</li><li>**64** for Shared drives</li><li>**128** for Classroom</li><li>**4096** for Chat</li></ul>|enum  |No|
|pageIndex|Sets the starting number of the page to get the jobs. The default value is 0.|integer|No|
|pageSize|Sets the number of jobs to display on one page. The default value is 100.|integer|No|
|jobType|Sets the job types that you want to get.<br> Valid values:<br> <ul><li> **1** for Backup</li><li> **2** for Restore </li><li> **3** for Export </li><li>**4** for Delete</li><li>**5** for Retention</li><li>**6** for Generate Report</li></ul>|enum  |No|
|startTime|Sets a start time (UTC time) for the time range in ISO 8601 format.|string|No|
|finishTime|Sets an end time (UTC time) for the time range in ISO 8601 format.|string|No|
|jobStatus| Sets the job status.<br>Valid values:</br> <ul><li> **0** for In progress</li><li> **2** for Finished</li><li>**3** for Failed </li><li>**7** for Finished with exception</li><ul>|enum |No|  

## Response

The API response provides detailed information about the jobs retrieved. Each job in the response includes various attributes that describe its properties and status.

| Elements           | Description                                                           | Type   | 
|--------------------|-----------------------------------------------------------------------|--------| 
|jobs                | A list containing job objects with detailed information.              | list  | 
|nextLink            | If multiple query requests are required to retrieve all the results, the response returns the **nextLink** property, and the **nextLink** value is a URL to the next page of results. You can retrieve the next page of results by sending the URL value of the **nextLink** property. | string |

**Job details**

Each job retrieved through the API includes detailed attributes that offer insights into its execution and outcome. These attributes assist in evaluating the performance, status, and specifics of each job, facilitating effective management and analysis.

| Elements           | Description                                                           | Type   |
|--------------------|-----------------------------------------------------------------------|--------|
| jobId              | Unique identifier for the job.                                        | string | 
| appType            | Service type of the job. <br> Valid values:<br> <ul><li> **1** for Gmail</li><li> **2** for Drive </li><li> **4** for Calendar </li><li>**8** for Contacts</li><li>**64** for Shared drives</li><li>**128** for Classroom</li><li>**4096** for Chat</li>                  | enum |
| jobType            | The  type of job performed. <br> Valid values:<br> <ul><li> **1** for Backup</li><li> **2** for Restore </li><li> **3** for Export </li><li>**4** for Delete</li><li>**5** for Retention</li><li>**6** for Generate Report</li></ul>| enum |
|dataSource|  The data source of the job. <br> Valid values:<br> <ul><li> **1** for Admin</li><li> **2** for ReCenter </li></ul>|enum  |
| status             | Status of the job.    <br>Valid values:</br> <ul><li> **0** for In progress</li><li> **2** for Finished</li><li>**3** for Failed </li><li>**7** for Finished with exception</li><ul>                                   | enum |
| progress           | The current state of the job by quantifying the percentage of completion. For example, if the value is **100.0**, it means that 100% of the tasks associated with the job have been completed.                               | double | 
| startTime          | The start time of the job in ISO 8601 format.                         | string | 
| finishTime         | The end time of the job in ISO 8601 format.                           | string |
| operator   | Name of the operator of the job.                                              | string | 

## Request Sample

The following request structure is designed to query a collection of jobs with flexible parameters, allowing you to refine your search based on various criteria. This request supports pagination and filtering to efficiently manage and retrieve job data. This request sample is an API call to the Cloud Backup for Google Workspace environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/backup/google/admin/jobs?pageindex=0&pagesize=10&apptype=1&jobtype=1&status=2&starttime=2024-12-12T00:00:00Z&finishtime=2024-12-13T00:00:00Z

```

## Response Sample

If successful, this method returns a 200 OK response code and a collection of  jobs in the response body.  
For details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code). 

```json
{
    "status": 200,
    "message": "",
    "jobs": [
        {
            "jobId": "GDIG20241009053431", // Job ID
            "appType": 1, // Service type of the job is Gmail
            "jobType": 5, // Type of the performed job is Retention
            "dataSource": 1, // Data source of the job is the Cloud Backup admin portal
            "status": 2, // Status of the job is Finished
            "progress": 100.0, // 100% of the tasks associated with the job have been completed
            "startTime": "2024-10-09T05:34:31+00:00", // UTC timestamp for the start time of the job
            "finishTime": "2024-10-09T05:50:36.008+00:00", // // UTC timestamp for the finished time of the job
            "operator": "System" // The job is operated by System
        },
        {
            "jobId": "GDIG20240909071817", // Job ID
            "appType": 1, // Service type of the job is Gmail
            "jobType": 5, // Type of the performed job is Retention
            "dataSource": 1, // Data source of the job is the Cloud Backup admin portal
            "status": 3, // Status of the job is Failed
            "progress": 100.0, // 100% of the tasks associated with the job have been completed
            "startTime": "2024-09-09T07:18:17+00:00", // UTC timestamp for the start time of the job
            "finishTime": "2024-09-09T07:22:34.984+00:00", // // UTC timestamp for the finished time of the job
            "operator": "System" // The job is operated by System
        }
    ],
    "nextLink": "5Q4WjfOaJ0YwYlq3J7HYvC3h%2BxgR7lllqb48ILCpWyebIQeNnukVgM72yyYiR6P2Hd1FBfsKTbh5pDP6j%2FZxloE%2BahKnVh7ZcSE8PGxRbH4OklY%2FQKphJG1%2FDmzyX7IAavZyGDCr0xcDgkX0j0ej2TUwdfu4puqtgRKJ%2FT41jdrgJ2WR9xnZSjT6UcjquKX4X%2By9kSzG7kM6N5XZIm3gXC%2Bg6CPFXllRr2dxBPVTnjkz" // Link to the next page of results
}
