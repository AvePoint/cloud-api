# Explore Insights for Microsoft 365 Public API  

## Export Methods

The AvePoint Graph Modern API provides a suite of export methods designed to facilitate the extraction of detailed reports and data insights. These methods enable users to export various types of reports, such as user permissions, group access, site permissions, sharing link permissions, and activity reports for specific objects. By leveraging these export methods, users can obtain comprehensive data for analysis, auditing, and integration with other systems or applications.

Each export method is tailored to address specific reporting needs, ensuring that users can retrieve the precise information required for their use cases. The API supports a range of query parameters to refine and customize the data retrieval process, allowing for targeted and efficient data exports.

The following sections provide detailed descriptions of each export method. These methods are essential tools for administrators and developers who need to manage and analyze permissions and activities within their AvePoint environments.

| API Method | Endpoint | Description |
| --- | --- | --- |
| [Export Activities on an Object](objects/objectActivities.md)| `/insights/activities/object/{path}/export`| Exports activities performed on a specific object.|
| [Export User Activities](users/userActivitiesExport.md) | `/insights/users/{email}/activities/export` | Exports activity data for a specific user. | 
| [Export User Permissions](users/userActivitiesExport.md)  |`/insights/users/{email}/access/export`|Exports user access report.|
| [Export Group Permissions](groups/groupAccesReport.md) | `/insights/groups/{groupId}/access/export` | Exports group access report. |
| [Export Site Permissions](sites/sitePermissionsExport.md) | `/insights/sites/permission/export` | Exports site permissions. |
| [Export Permission-Related Information for Sharing Links](sharingLinks/linkExport.md) | `/insights/sharingLinks/export` | Exports permission-related information for sharing links |

## API Methods for Direct Data Retrieval

In addition to the export methods, the Insights for Microsoft 365 Modern API provides several methods that allow users to retrieve data directly in the response. These methods are designed for real-time data access and provide immediate insights without the need for export jobs. 

| API Method | Endpoint | Documentation |
| --- | --- | --- |
| [Retrieve User Permissions](users/userPermissions.md) | `/insights/users/access` | Retrieves the permission-related information for specific users. | 
| [Retrieve User Summary](users/userSummary.md)  |`/insights/users/summary`|Retrieves the user summary information.|
| [Retrieve Group Summary](groups/groupSummary.md) | `/insights/groups/summary` | Retrieves group summary. |
| [Retrieve Site Permissions](sites/sitePermissionsGet.md) | `/insights/sites/permission` | Retrieve site Permissions. |
| [Retrieve Site Overview](sites/siteOverview.md) | `/insights/sites/overview` | Retrieves site overview. |  
| [Retrieve Site ID](sites/siteId.md) | `/insights/sites/overview` | Retrieves site ID. |
| [Retrieve Site Detail Records](sites/siteDetailRecords.md)| `insights/sites/{siteId}/detailRecords`| Retrieves site detail records.|
| [Retrieve Permission-Related Information for Sharing Links](sharingLinks/linkSummary.md) | `/insights/sharingLinks/{siteUrl}/summary` | Retrieves the link summaries. |


