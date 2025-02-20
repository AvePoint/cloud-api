# Retrieve Group Summary

This API method (`/insights/groups/summary` navigation property) retrieves the group summary information. This method is useful for obtaining an overview of group properties and statuses. 

## Permission 

The following permission is required to call this API.  
You must register an app through AvePoint Online Services > App registration to authenticate and authorize your access to AvePoint Graph API. For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API     | Permission required | 
|-------------------|---------------|
| `/insights/groups/summary` | insights.graph.readwrite.all  |

## Request 

This section outlines the HTTP method and endpoint used to retrieve group summary information. It provides a concise description of the action performed by the API call. 

| HTTP Method | Endpoint | Description |
| --- | --- | --- |
| GET | `/insights/groups/summary` | Retrieves the group summary information. |


## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process. These parameters allow users to specify pagination and page size to filter the results effectively.


| Parameter | Description | Type    | Required? |
|-----------|-------------|---------|-----------|
| startPage | The starting page of the query. | integer | Yes        |
| pageSize  | Sets the number of results for one page. 100 results on one page at most. | integer | Yes        |

## Responses

The API response provides detailed information about the groups retrieved. Each group in the response includes various attributes that describe its properties and status.

| Elements | Description                                      | Type    |
|----------|--------------------------------------------------|---------|
| status   | The HTTP response status code                    | integer |
| message  | The error message                             | string  |
| nextLink | The token to be used to get the remaining results of this request | string  |
| values   | A list of group summary objects               | list   |

**Group summary**

| Elements | Description                                      | Type    |
|----------|--------------------------------------------------|---------|
|displayName   |  Display name of the group | string|
|groupId| Group ID|string|
|email| The group email address |string |
|groupType| The group type|sting|
|membershipType| The membership type of the group|string|
|createdOn| The created time of the group|string|
|externalMemberCount|The number of the external users in the group|integer |


## Request Sample

To use this API, send a `GET` request to the specified endpoint, including necessary parameters as defined. This will return the relevant group summary details in a structured format, enabling easy integration with other systems or applications. 

```json
https://graph-us.avepointonlineservices.com/insights/groups/summary?startPage=1&pageSize=50
```

## Response Sample  

The following is a sample response for this API method, which includes summary information of the groups retrieved: 

```json
{
    "values": [
        {
            "displayName": "SCgroup********",     //Group name
            "groupId": "84888488-8488-8488-8488-848884888488",    //Microsoft Entra Group ID
            "email": null,    //Group email
            "groupType": "Security Group", //Group type
            "membershipType": "Assigned",    //Membership type
            "createdOn": "2022-03-07T08:19:41",//Created  time
            "externalMemberCount": 17    //External member count
        },
        {
            "displayName": "******** Mail-Enabled Security Groups02",
            "groupId": "0e4a0e4a-0e4a-0e4a-0e4a-0e4a0e4a0e4a",
            "email": "Mar2022M********@m365x***63.onmicrosoft.com",
            "groupType": "Mail-enabled security group",
            "membershipType": "Assigned",
            "createdOn": "2022-03-03T01:11:26",
            "externalMemberCount": 15
        },
        {
            "displayName": "*****Distribution Group01",
            "groupId": "7bc05c3d-930e-496e-b9b0-f6f8ff1b02a7",
            "email": "Mar2022**************01@m365x****63.onmicrosoft.com",
            "groupType": "Distribution group",
            "membershipType": "Assigned",
            "createdOn": "2022-03-03T01:08:58",
            "externalMemberCount": 11
        },
        {
            "displayName": "SCgroup*******",
            "groupId": "d26ad26a-d26a-d26a-d26a-d26ad26ad26a",
            "email": null,
            "groupType": "Security Group",
            "membershipType": "Dynamic",
            "createdOn": "2022-03-02T08:55:50",
            "externalMemberCount": 10
        },
        {
            "displayName": "********Public Group03",
            "groupId": "cf08cf08-cf08-cf08-cf08-cf08cf08cf08",
            "email": "May202****@insights*****.onmicrosoft.com",
            "groupType": "Microsoft 365 Group",
            "membershipType": "Assigned",
            "createdOn": "2022-03-04T03:45:40",
            "externalMemberCount": 7
        }
    ],
    "status": 200,
    "message": "",
    "nextLink": null
}
