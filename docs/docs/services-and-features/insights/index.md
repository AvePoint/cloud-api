# Explore Insights for Microsoft 365 Public API  

## Export Methods

The AvePoint Graph Modern API provides a suite of export methods designed to facilitate the extraction of detailed reports and data insights. These methods enable users to export various types of reports, such as user permissions, group access, site permissions, sharing link permissions, and activity reports for specific objects. By leveraging these export methods, users can obtain comprehensive data for analysis, auditing, and integration with other systems or applications.

Each export method is tailored to address specific reporting needs, ensuring that users can retrieve the precise information required for their use cases. The API supports a range of query parameters to refine and customize the data retrieval process, allowing for targeted and efficient data exports.

The following sections provide detailed descriptions of each export method, including the required permissions, query parameters, and the structure of the responses. These methods are essential tools for administrators and developers who need to manage and analyze permissions and activities within their AvePoint environments.


## API Methods for Direct Data Retrieval

In addition to the export methods, the Insights for Microsoft 365 Modern API provides several methods that allow users to retrieve data directly in the response. These methods are designed for real-time data access and provide immediate insights without the need for export jobs. 

| API Method | Endpoint | Documentation |
| --- | --- | --- |
| **Get User Permissions** | `/insights/users/access` | [userPermissions.md](insights/users/userPermissions.md) | 
| **Get User Summary**  |`/insights/users/summary`|[userSummary.md](insights/users/userSummary.md)|
| **Get Group Summary** | `/insights/groups/summary` | [groupAccessReport.md](insights/groups/groupAccessReport.md) |
| **Get Site Permissions** | `/insights/sites/permission` | [sitePermissions.md](insights/sites/sitePermissions.md) |
| **Get Site Overview** | `/insights/sites/overview` | [siteOverview.md](insights/sites/siteOverview.md) |  
| **Get Site ID** | `/insights/sites/overview` | [siteID.md](insights/sites/siteId.md) |
| **Get Permission-Related Information for Sharing Links** | `/insights/sharingLinks/{siteUrl}/summary` | [sharingLinks.md](insights/sharingLinks/sharingLinks.md) |

| **Get Activities for a Specific Object** | `/insights/activities/object/{path}` | [objectActivities.md](insights/activities/objectActivities.md) |

