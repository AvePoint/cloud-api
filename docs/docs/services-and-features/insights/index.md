# Explore Insights Public API  

Welcome to the comprehensive guide for the Insights Public API. This documentation provides detailed information on how to leverage the API to extract, manage, and analyze data within your Microsoft 365 or Google environment. Whether you are an administrator looking to audit permissions, a developer integrating data into other systems, or an analyst seeking detailed reports, this guide will help you navigate the various export and data retrieval methods available. Dive in to explore the powerful tools and capabilities that the Insights API offers to enhance your data management and analysis workflows.


## API Methods for Starting Export Report Jobs

The Insights API provides a suite of export methods designed to facilitate the extraction of detailed reports and data insights. These methods enable users to export various types of reports, such as user activities, user permissions, group access, site permissions, sharing link permissions, and activity reports for specific objects. By leveraging these export methods, users can obtain comprehensive data for analysis, auditing, and integration with other systems or applications.

Each export method is tailored to address specific reporting needs, ensuring that users can retrieve the precise information required for their use cases. The API supports a range of query parameters to refine and customize the data retrieval process, allowing for targeted and efficient data exports.

The following sections provide detailed descriptions of each export method. These methods are essential tools for administrators and developers who need to manage and analyze permissions and activities within their AvePoint environments.

Endpoint | API Method |  Description |
| --- | --- | --- |
| `/insights/activities/object/{path}/export`| [Export Activities for a Specific Object](objects/objectActivities.md)| Exports activities performed on a specific object.|
| `/insights/users/{email}/activities/export`| [Export User Activities](users/userActivitiesExport.md)  | Exports activity data for a specific user. | 
|`/insights/users/{email}/access/export`| [Export User Permissions](users/userPermissionsExport.md)  |Exports user access report.|
| `/insights/groups/{groupId}/access/export`| [Export Group Access Permissions](groups/groupAccessReport.md)  | Exports group access report. |
| `/insights/sites/permission/export` | [Export Site Permissions](sites/sitePermissionsExport.md) | Exports site permissions. |
| `/insights/sharingLinks/export` | [Export Permission-Related Information for Sharing Links](sharingLinks/linkExport.md) | Exports permission related information for sharing links. |
| `/insights/google/activities/object/{id}/export`| [Export Activities for a Specific Google Object](objects/googleObjectActivities.md)| Exports activities performed on a specific Google object.|
| `/insights/google/users/{email}/activities/export`| [Export Google User Activities](users/googleUserActivitiesExport.md)  | Exports activity data for a specific Google user. | 
|`/insights/google/users/{email}/access/export`| [Export Google User Permissions](users/googleUserPermissionsExport.md)  |Exports Google user access report.|
| `/insights/google/groups/{groupId}/access/export`| [Export Google Group Access Permissions](groups/googleGroupAccessReport.md)  | Exports Google group access report. |
| `/insights/google/drives/permission/export` | [Export Drive Permissions](drives/drivePermissionsExport.md) | Exports Google drive permissions. |
| `/insights/google/sharingLinks/export` | [Export Permission-Related Information for Google Sharing Links](sharingLinks/googleLinkExport.md) | Exports permission related information for Google sharing links. |

## API Methods for Direct Data Retrieval

In addition to the export methods, the Insights API provides several methods that allow users to retrieve data directly in the response. These methods are designed for real-time data access and provide immediate insights without the need for export jobs. 

| Endpoint| API Method  | Description |
| --- | --- | --- |
| `/insights/users/access`| [Retrieve User Permissions](users/userPermissions.md)  | Retrieves the permission-related information for specific users. | 
|`/insights/users/summary`| [Retrieve User Summary](users/userSummary.md)  |Retrieves the user summary information.|
| `/insights/groups/summary`| [Retrieve Group Summary](groups/groupSummary.md)  | Retrieves group summary. |
| `/insights/sharingLinks/summary`| [Retrieve Sharing Links Summary](sharingLinks/linkSummary.md)  | Retrieves link summaries. |
| `/insights/sites/permission`| [Retrieve Site Permissions](sites/sitePermissionsGet.md)  | Retrieves site Permissions. |
| `/insights/sites/overview` | [Retrieve Site Overview](sites/siteOverview.md) | Retrieves site overview. |  
| `/insights/sites/{siteUrl}/siteId`| [Retrieve Site ID](sites/siteId.md)  | Retrieves site ID. |
| `insights/sites/detailRecords`| [Retrieve Site Detail Records](sites/siteDetailRecords.md)| Retrieves site detail records.|
| `/insights/sharingLinks/{siteUrl}/summary`| [Retrieve Permission-Related Information for Sharing Links](sharingLinks/linkSummary.md)  | Retrieves the link summaries. |

## API Methods for Direct Action

The Insights API provides the method that allow users to download the report file of an export job, and the method to add tags to objects for data categorization and further management. 

| Endpoint| API Method  | Description |
| --- | --- | --- |
| `/insights/job/{jobId}/exportfile`| [Download Export Job File](exportJobs/exportJobFile.md)  | Downloads the report file of an export job. | 
|`/insights/sites/{siteId}/{objectUrl}/settag`| [Add Tag to Specific Object](objects/setTag.md)  |Adds a tag to a specific object.|



