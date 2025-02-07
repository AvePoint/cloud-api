# Explore Insights for Microsoft 365 Public API  

Welcome to the comprehensive guide for the Insights for Microsoft 365 Public API. This documentation provides detailed information on how to leverage the AvePoint Graph Modern API to extract, manage, and analyze data within your Microsoft 365 environment. Whether you are an administrator looking to audit permissions, a developer integrating data into other systems, or an analyst seeking detailed reports, this guide will help you navigate the various export and data retrieval methods available. Dive in to explore the powerful tools and capabilities that the Insights API offers to enhance your data management and analysis workflows.


## API Methods for Starting Export Report Jobs

The Insights for Microsoft 365 Modern API provides a suite of export methods designed to facilitate the extraction of detailed reports and data insights. These methods enable users to export various types of reports, such as user permissions, group access, site permissions, sharing link permissions, and activity reports for specific objects. By leveraging these export methods, users can obtain comprehensive data for analysis, auditing, and integration with other systems or applications.

Each export method is tailored to address specific reporting needs, ensuring that users can retrieve the precise information required for their use cases. The API supports a range of query parameters to refine and customize the data retrieval process, allowing for targeted and efficient data exports.

The following sections provide detailed descriptions of each export method. These methods are essential tools for administrators and developers who need to manage and analyze permissions and activities within their AvePoint environments.

Endpoint | API Method |  Description |
| --- | --- | --- |
| `/insights/activities/object/{path}/export`| [Export Activities on an Object](objects/objectActivities.md)| Exports activities performed on a specific object.|
| `/insights/users/{email}/activities/export`| [Export User Activities](users/userActivitiesExport.md)  | Exports activity data for a specific user. | 
|`/insights/users/{email}/access/export`| [Export User Permissions](users/userPermissionsExport.md)  |Exports user access report.|
| `/insights/groups/{groupId}/access/export`| [Export Group Permissions](groups/groupAccesReport.md)  | Exports group access report. |
| `/insights/sites/permission/export` | [Export Site Permissions](sites/sitePermissionsExport.md) | Exports site permissions. |
| `/insights/sharingLinks/export` | [Export Permission-Related Information for Sharing Links](sharingLinks/linkExport.md) | Exports permission-related information for sharing links |

## API Methods for Direct Data Retrieval

In addition to the export methods, the Insights for Microsoft 365 Modern API provides several methods that allow users to retrieve data directly in the response. These methods are designed for real-time data access and provide immediate insights without the need for export jobs. 

| Endpoint| API Method  | Description |
| --- | --- | --- |
| `/insights/users/access`| [Retrieve User Permissions](users/userPermissions.md)  | Retrieves the permission-related information for specific users. | 
|`/insights/users/summary`| [Retrieve User Summary](users/userSummary.md)  |Retrieves the user summary information.|
| `/insights/groups/summary`| [Retrieve Group Summary](groups/groupSummary.md)  | Retrieves group summary. |
| `/insights/sites/permission`| [Retrieve Site Permissions](sites/sitePermissionsGet.md)  | Retrieve site Permissions. |
| `/insights/sites/overview` | [Retrieve Site Overview](sites/siteOverview.md) | Retrieves site overview. |  
| `/insights/sites/overview`| [Retrieve Site ID](sites/siteId.md)  | Retrieves site ID. |
| `insights/sites/{siteId}/detailRecords`| [Retrieve Site Detail Records](sites/siteDetailRecords.md)| Retrieves site detail records.|
| `/insights/sharingLinks/{siteUrl}/summary`| [Retrieve Permission-Related Information for Sharing Links](sharingLinks/linkSummary.md)  | Retrieves the link summaries. |


