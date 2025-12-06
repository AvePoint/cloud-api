# Retrieve Power Pages Site Details

Use this API to access and retrieve details of your Power Pages sites.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.  
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#authentication-and-authorization).

| API    | Permission |
|-------------------|---------------|
|`/smp/powerplatform/powerpages` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your Power Pages sites.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/powerplatform/powerpages` | Retrieves your Power Pages sites' information | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of Power Pages sites retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of sites are retrieved. By default, sites of all tenants are retrieved. | string | No |

## Responses

The API response provides detailed information about the Power Pages sites retrieved. Each site in the response includes various attributes that describe its properties and status.

| **Elements**              | **Description**                                                                 | **Type**   |
|---------------------------|--------------------------------------------------------------------------------|------------|
| id                        | The unique identifier for the Power Page.                                      | string     |
| tenantId                  | The unique identifier of the tenant that the site belongs to.                  | string     |
| tenantName                | The name of the tenant that the site belongs to.                               | string     |
| containerId               | The unique identifier of the container that the site belongs to.               | string     |
| containerName             | The name of the container that the site belongs to.                            | string     |
| siteId                    | The unique identifier for the site                                             |            |
| environmentId             | The unique identifier of the environment that the site belongs to.             | string     |
| environmentName           | The name of the environment that the site belongs to.                          | string     |
| name                      | The display name of the site.                                                  | string     |
| websiteName               | The internal system name of the site.                                          | string     |
| templateName              | The template used to create the site.                                          | string     |
| websiteUrl                | The primary public URL or hostname configured for the site.                    | string     |
| defaultLanguage           | The default language configured for the site.                                  | string     |
| type                      | The type of the site.                                                          | string     |
| earlyUpgradeEnabled       | Indicates whether early upgrade or preview feature updates are enabled.        | boolean    |
| ownerId                   | The unique identifier of the site owner.                                       | string     |
| ownerDisplayName          | The display name of the site owner.                                            | string     |
| ownerDepartment           | The department of the site owner.                                              | string     |
| ownerOffice               | The office of the site owner.                                                  | string     |
| siteVisibility            | The visibility of the site.                                                    | string     |
| dataModel                 | The data model architecture of the site.                                       | string     |
| anonymousAccess           | Indicates whether anonymous (unauthenticated) users can access public pages.   | string     |
| createdTime               | The date and time when the site was created.                                   | string     |
| creatorId                 | The unique identifier of the user who created the site.                        | string     |
| creatorDisplayName        | The display name of the user who created the site.                             | string     |
| creatorUserPrincipalName  | The user principal name (UPN) of the site creator.                             | string     |
| creatorDepartment         | The department of the site creator.                                            | string     |
| creatorCountry            | The country of the site creator.                                               | string     |
| creatorJobTitle           | The job title of the site creator.                                             | string     |
| creatorEmail              | The email address of the site creator.                                         | string     |
| creatorOffice             | The office location of the site creator.                                       | string     |
| modifiedTime              | The date and time when the site was last modified.                             | string     |
| modifiedId                | The unique identifier of the user who last modified the site.                  | string     |
| modifiedDisplayName       | The display name of the user who last modified the site.                       | string     |
| siteStatus                | The operational state of the site.                                             | string     |
| activationStatus          | Indicates whether the site has been activated and is currently available.      | string     |
| activitiesLast7Days       | The number of activities in the last 7 days.                                   | integer    |
| activitiesLast30Days      | The number of activities in the last 30 days.                                  | integer    |
| activitiesLast90Days      | The number of activities in the last 90 days.                                  | integer    |
| activitiesLast180Days     | The number of activities in the last 180 days.                                 | integer    |

## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/powerplatform/powerpages
```
## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-API.html#http-status-code).

```json
{
  "powerPages": [
    {
      "id": "", // The unique identifier for the Power Page
      "tenantId": "", // The unique identifier of the tenant that the site belongs to
      "tenantName": "", // The name of the tenant that the site belongs to
      "containerId": "", // The unique identifier of the container that the site belongs to
      "containerName": "", // The name of the container that the site belongs to
      "siteId": "", // The unique identifier for the site
      "environmentId": "", // The unique identifier of the environment that the site belongs to
      "environmentName": "", // The name of the environment that the site belongs to
      "name": "", // The display name of the site
      "websiteName": "", // The internal system name of the site
      "templateName": "", // The template used to create the site
      "websiteUrl": "", // The primary public URL or hostname configured for the site
      "defaultLanguage": "", // The default language configured for the site
      "type": "", // The type of the site
      "earlyUpgradeEnabled": false, // Indicates whether early upgrade or preview feature updates are enabled
      "ownerId": "", // The unique identifier of the site owner
      "ownerDisplayName": "", // The display name of the site owner
      "ownerDepartment": "", // The department of the site owner
      "ownerOffice": "", // The office of the site owner
      "siteVisibility": "", // The visibility of the site
      "dataModel": "", // The data model architecture of the site
      "anonymousAccess": "", // Indicates whether anonymous (unauthenticated) users can access public pages
      "createdTime": "", // The date and time when the site was created
      "creatorId": "", // The unique identifier of the user who created the site
      "creatorDisplayName": "", // The display name of the user who created the site
      "creatorUserPrincipalName": "", // The user principal name (UPN) of the site creator
      "creatorDepartment": "", // The department of the site creator
      "creatorCountry": "", // The country of the site creator
      "creatorJobTitle": "", // The job title of the site creator
      "creatorEmail": "", // The email address of the site creator
      "creatorOffice": "", // The office location of the site creator
      "modifiedTime": "", // The date and time when the site was last modified
      "modifiedId": "", // The unique identifier of the user who last modified the site
      "modifiedDisplayName": "", // The display name of the user who last modified the site
      "siteStatus": "", // The operational state of the site
      "activationStatus": "", // Indicates whether the site has been activated and is currently available
      "activitiesLast7Days": 0, // The number of activities in the last 7 days
      "activitiesLast30Days": 0, // The number of activities in the last 30 days
      "activitiesLast90Days": 0, // The number of activities in the last 90 days
      "activitiesLast180Days": 0, // The number of activities in the last 180 days
    }
  ],
  "totalCount": 1,
  "nextLink": ""
}

