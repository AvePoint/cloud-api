# Graph API for Insights
An ASP.NET Core Graph API for Insights

## Version: v2

### Terms of service
https://insights.avepointonlineservices.com/

### /activities/object/{path}/export

#### GET
##### Summary:

Get object activity

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| path | path | Filter by path | Yes | string |
| startTime | query | Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss" | No | string |
| finishTime | query | Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss" | No | string |
| eventTypes | query | Filter by Event Type | No | [ string ] |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /groups/summary

#### GET
##### Summary:

Gets the summary of specific groups.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| startPage | query |  | No | integer |
| pageSize | query |  | No | integer |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /groups/{groupId}/access/export

#### GET
##### Summary:

Gets the .zip file from exporting the permission related information of specific groups.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| groupId | path | Sets the email addresses or group Id or group logonname of group for which you want to export the permission report | Yes | string |
| exportOptionType | query | So far support:  1 - for exporting both the summary report and site collection level access report  2 - for exporting both the summary report and access report to all objects in the configured data scope  3 - for only exporting the summary report | No | [ExportOptionType](#exportoptiontype) |
| siteUrls | query | Sets the URLs of site collections for which you want to export the permission report. | No | [ string ] |
| dataSources | query | Sets the workspace in which you want to export the access report of users. Multiple values are allowed.  microsoft teams   sharepoint online  onedrive for business  microsoft 365 group | No | [ string ] |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /Healthz

#### GET
##### Summary:

The API is for check health of API service

##### Description:

GET: /healthz

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /job/{jobId}/exportstatus

#### GET
##### Summary:

Get Activity export job statuts

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| jobId | path | Job Id | Yes | integer |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /job/{jobId}/exportfile

#### GET
##### Summary:

Download Activity export  file

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| jobId | path | Job Id | Yes | integer |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /sharingLinks/{siteUrl}/summary

#### GET
##### Summary:

Gets the summary of specific links.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| siteUrl | path | Sets the URL of site collections for which you want to get the summary information. | Yes | string |
| linkType | query | Sets the link types that you are about to get.  External Link = 32  Organization Link = 64  Anonymous Link = 128 | No | integer |
| pageSize | query | Sets the number of links displayed in each page of the result. The number must be no larger than 100. | No | integer |
| nextLink | query | Sets whether to get the remaining results of a request of which the results are more than 100. | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /sharingLinks/export

#### GET
##### Summary:

Gets the .zip file from exporting the permission related information of specific links.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| exportLinkType | query | Set export type  32 (for FlexibleLink link)  64 (for organization link)  128 (for external link) | No | [PrincipalTypes](#principaltypes) |
| startTime | query | Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss" | No | string |
| finishTime | query | Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss" | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /sites/permission

#### GET
##### Summary:

Gets the permission-related information of specific site collections.

##### Description:

The api/v1/site/permission/export API is recommended when the site collections that you are about to export are over 2,000.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| siteUrls | query | Sets the URLs of site collections for which you want to get the permission related information | No | [ string ] |
| pageSize | query | Sets whether to get the remaining results of a request of which the results are more than 100. | No | integer |
| nextLink | query | Sets the number of results for one page. 100 results on one page at most. | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /sites/permission/export

#### GET
##### Summary:

Exports the permission reports of specific site collections.

##### Description:

You can only export permission reports of 100 site collections at a time.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| siteUrls | query | Sets the URLs of site collections for which you want to export the permission report. | No | [ string ] |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /sites/overview

#### GET
##### Summary:

Get sites data

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| riskLevel | query | Enter the set of risk levels. | No | [ integer ] |
| nextLink | query | Sets the number of results for one page. 100 results on one page at most. | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /sites/{siteUrl}/siteid

#### GET
##### Summary:



##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| siteUrl | path | sharepoint site uri | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /sites/{siteId}/detailrecords

#### GET
##### Summary:



##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| siteId | path | sharepoint site Id | Yes | string |
| nextLink | query | Sets the number of results for one page. 100 results on one page at most. | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /sites/{siteId}/{objectUrl}/settag

#### PATCH
##### Summary:

object add tag

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| siteId | path | sharepoint site Id | Yes | string |
| objectUrl | path | sharepoint object url | Yes | string |
| tagName | query | tag name | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /users/summary

#### GET
##### Summary:

Gets the summary of specific users.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| startPage | query | The starting page of the query starts from 0. | No | integer |
| pageSize | query | Sets the number of results for one page. 100 results on one page at most. | No | integer |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /users/access

#### GET
##### Summary:

Gets the permission-related information of specific users.

##### Description:

The api/v1/user/permission/export API is recommended when the users that you are about to export are over 2,000.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| siteUrls | query | Sets the URLs of site collections for which you want to get the permission related information | No | [ string ] |
| emails | query | Sets the email addresses of users for which you want to export the permission report | No | [ string ] |
| nextLink | query | Sets whether to get the remaining results of a request of which the results are more than 100. | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /users/{email}/access/export

#### GET
##### Summary:

Exports the access reports of specific users in different workspaces.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| email | path | Sets the email addresses of users for which you want to export the permission report | Yes | string |
| siteUrls | query | Sets the URLs of site collections for which you want to export the permission report. | No | [ string ] |
| dataSources | query | Sets the workspace in which you want to export the access report of users. Multiple values are allowed.  microsoft teams   sharepoint online  onedrive for business  microsoft 365 group | No | [ string ] |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### /users/{email}/activities/export

#### GET
##### Summary:

get user activity

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| email | path | Filter by email | Yes | string |
| startTime | query | Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss" | No | string |
| finishTime | query | Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss" | No | string |
| eventTypes | query | Filter by Event Type | No | [ string ] |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK |

### Models


#### AccessViewModule

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| module | string | The data source. | No |
| siteName | string | The name of the site. | No |
| name | string | The name of the permission. | No |
| location | string | The URL of the object. | No |
| objectType | string | The object type. | No |
| inheritType | string | The status whether the permission is inherited. | No |
| permission | string | The permission. | No |
| sensitivityLevel | string | The sensitivity level of the object. | No |
| sensitiveInfoType | string | The sensitive info type of the object. | No |
| isDirect | boolean | The status whether the permission is directly granted. | No |
| sensitivityLabel | string | The sensitivity label of the object. | No |
| inheritedFrom | string | The parent from which the permission inherits. | No |

#### AccessViewModuleJsonResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| nextLink | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| values | [ [AccessViewModule](#accessviewmodule) ] |  | No |

#### AccessViewModuleOptions

Get access report by using the paging option

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| language | string | Sets the language of the report you are about to export.  <value>Default: en-US Support: en-US/ja-JP/fr-FR</value> | No |
| siteUrls | [ string ] | Sets the URLs of site collections for which you want to get the permission related information. 100 URLs at most. | No |
| emails | [ string ] | Sets the email addresses of users for which you want to export the permission report. 100 email addresses at most. | No |
| token | string | Sets whether to get the remaining results of a request of which the results are more than 100. | No |
| top | integer | Sets the number of results for one page. 100 results on one page at most. | No |

#### AccessViewModuleResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| content | string | The remark. The element is not used for this API and responded with “null” by default. | No |
| nextToken | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| results | [ [AccessViewModule](#accessviewmodule) ] |  | No |

#### ActivityExportOptions

Activity export  Options

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| language | string | Sets the language of the report you are about to export.  <value>Default: en-US Support: en-US/ja-JP/fr-FR</value> | No |
| startTime | string | Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss" | No |
| endTime | string | Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss" | No |
| eventTypes | [ string ] | Filter by Event Type | No |
| path | string | Filter by Path | No |
| email | string | Filter by User email | No |

#### BooleanJsonResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| nextLink | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| values | [ boolean ] |  | No |

#### DetailRecordData

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| id | string |  | No |
| name | string |  | No |
| location | string |  | No |
| objectType | string |  | No |
| createdBy | string |  | No |
| module | string |  | No |
| inheritType | string |  | No |
| siteName | string |  | No |
| sensitivityLevel | string |  | No |
| exposureLevel | string |  | No |
| scannedTime | string |  | No |
| createdTime | string |  | No |
| modifiedTime | string |  | No |
| channelName | string |  | No |
| riskLevel | string |  | No |
| privacy | string |  | No |
| sensitiveInfoType | [ string ] |  | No |
| sensitivityLabel | string |  | No |
| tagName | string |  | No |
| retentionLabel | string |  | No |
| creatorEmail | string |  | No |
| webUrl | string |  | No |

#### DetailRecordDataJsonResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| nextLink | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| values | [ [DetailRecordData](#detailrecorddata) ] |  | No |

#### DetailRecordDataResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| content | string | The remark. The element is not used for this API and responded with “null” by default. | No |
| nextToken | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| results | [ [DetailRecordData](#detailrecorddata) ] |  | No |

#### DetailRecordExportOptions

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| token | string |  | No |
| pageSize | integer |  | No |
| filters | [ [Filter](#filter) ] |  | No |
| language | string |  | No |
| siteId | string |  | No |

#### ExportOptionType

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| ExportOptionType | integer |  |  |

#### ExportOptions

Export job option

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| language | string | Sets the language of the report you are about to export.  <value>Default: en-US Support: en-US/ja-JP/fr-FR</value> | No |
| siteUrls | [ string ] | Sets the URLs of site collections for which you want to export the permission report.   <value>100 URLs at most.</value> | No |
| emails | [ string ] | Sets the email addresses of users for which you want to export the permission report.   <value>  100 email addresses at most.  </value> | No |
| dataSources | [ string ] | Sets the workspace in which you want to export the access report of users. Multiple values are allowed.  <value>  microsoft teams   sharepoint online  onedrive for business  microsoft 365 group  </value> | No |
| exportOptionType | [ExportOptionType](#exportoptiontype) |  | No |
| exportLinkType | [PrincipalTypes](#principaltypes) |  | No |
| startTime | string | Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss" | No |
| endTime | string | Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss" | No |

#### ExportOptionsBase

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| token | string |  | No |
| pageSize | integer |  | No |
| filters | [ [Filter](#filter) ] |  | No |

#### ExportResult

Export Job Result

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| getFileUrl | string | Download file request Uri | No |
| id | integer | Export Job Id | No |

#### Filter

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| id | string |  | No |
| values | [ string ] |  | No |

#### GroupSummaryViewModule

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| displayName | string | The group name. | No |
| groupId | string | The group ID. | No |
| email | string | The email address of the group | No |
| groupType | string | The type of the group.  <value>  Microsoft 365 Group  Security Group  Distribution Group  Mail-enabled Security Group  </value> | No |
| membershipType | string | The membership type of the group:  <value>  Assigned  Dynamic  </value> | No |
| createdOn | dateTime | The time when the group is created. | No |
| externalMemberCount | integer | The number of external users in the group. | No |

#### GroupSummaryViewModuleJsonResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| nextLink | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| values | [ [GroupSummaryViewModule](#groupsummaryviewmodule) ] |  | No |

#### GroupSummaryViewModuleResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| content | string | The remark. The element is not used for this API and responded with “null” by default. | No |
| nextToken | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| results | [ [GroupSummaryViewModule](#groupsummaryviewmodule) ] |  | No |

#### InsightsExportResult

Insights Export Job Result

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | Export Status  <value>  None = 0,  Inprogress = 1,  Successful = 2,  Failed = 3,  SuccessWithException = 4,  Stopping = 5,  Stopped = 6  </value> | No |
| description | string | Status Text | No |

#### Int32JobStatusResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| jobStatus | integer |  | No |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |

#### LinkViewModule

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| id | string | The ID in the link summary. | No |
| siteId | string | The site ID in which the object is shared by the link. | No |
| selfId | string | The selfID of the object which is shared by the link. | No |
| linkId | string | The link ID. | No |
| logonName | string | The link login name. | No |
| createTime | dateTime | The time when the link is created. | No |
| expireTime | dateTime | The time when the link is expired.  This is only available for anonymous links. | No |
| name | string | The object name that is shared via the link. | No |
| objectUrl | string | The object URL that is shared via the link. | No |
| linkType | string | The link type.  <value>  32(for flexible link)  64 (for organization link)  128 (for anonymous link)  </value> | No |
| shareBy | string | The user who created the link. | No |
| inheritFrom | string | The parent from which the permission inherits. | No |
| inheritType | string | The status whether the permission is inherited. | No |
| shareWith | integer | The number of users and groups with whom the link is shared. | No |
| linkUrl | string | The link URL. | No |
| permission | string | The permission with which the link is shared. | No |
| fileType | string | The type of the object shared via the link. | No |
| sensitivityLevel | string | The sensitivity level of the object shared via the link. | No |

#### LinkViewModuleJsonResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| nextLink | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| values | [ [LinkViewModule](#linkviewmodule) ] |  | No |

#### LinkViewModuleOptions

Get links by using the paging option

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| language | string | Sets the language of the report you are about to export.  <value>Default: en-US Support: en-US/ja-JP/fr-FR</value> | No |
| siteUrls | [ string ] | Sets the URLs of site collections for which you want to get the summary information. | No |
| token | string | Sets whether to get the remaining results of a request of which the results are more than 100. | No |
| pageSize | integer | Sets the number of links displayed in each page of the result. The number must be no larger than 100. | No |
| linkType | integer |  Sets the link types that you are about to get.   <value>  External Link = 32  Organization Link = 64  Anonymous Link = 128  </value> | No |

#### LinkViewModuleResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| content | string | The remark. The element is not used for this API and responded with “null” by default. | No |
| nextToken | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| results | [ [LinkViewModule](#linkviewmodule) ] |  | No |

#### PrincipalTypes

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| PrincipalTypes | integer |  |  |

#### SitePermissionViewModule

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| module | string | The data source. | No |
| name | string | The name of the permission. | No |
| url | string | The URL of the object. | No |
| objectType | string | The object type. | No |
| principalName | string | The name of the user or group. | No |
| email | string | Email | No |
| principalType | string | The type of the user or group. | No |
| permission | string | The permission. | No |
| numberOfMembers | integer | The number of members in the group. | No |
| isExternalUser | boolean | The status whether external users exist. | No |
| inheritType | string | The status whether the permission is inherited. | No |
| linkGivingAccessTo | string | The members that are given the permission via link. | No |

#### SitePermissionViewModuleJsonResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| nextLink | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| values | [ [SitePermissionViewModule](#sitepermissionviewmodule) ] |  | No |

#### SitePermissionViewModuleOptions

Export permission report by using the paging option
///

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| language | string | Sets the language of the report you are about to export.  <value>Default: en-US Support: en-US/ja-JP/fr-FR</value> | No |
| siteUrls | [ string ] | Sets the URLs of site collections for which you want to get the permission related information. 100 URLs at most. | No |
| token | string | Sets whether to get the remaining results of a request of which the results are more than 100. | No |
| top | integer | Sets the number of results for one page. 100 results on one page at most. | No |

#### SitePermissionViewModuleResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| content | string | The remark. The element is not used for this API and responded with “null” by default. | No |
| nextToken | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| results | [ [SitePermissionViewModule](#sitepermissionviewmodule) ] |  | No |

#### SiteResponseViewModel

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| siteId | string |  | No |
| siteUrl | string |  | No |

#### SiteResponseViewModelResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| content | string | The remark. The element is not used for this API and responded with “null” by default. | No |
| nextToken | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| results | [ [SiteResponseViewModel](#siteresponseviewmodel) ] |  | No |

#### SiteUrlRequest

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| siteUrls | [ string ] |  | No |

#### SitesData

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| siteName | string |  | No |
| siteUrl | string |  | No |
| riskItemCount | integer |  | No |
| sensitiveItemCount | integer |  | No |
| exposureItemCount | integer |  | No |

#### SitesDataJsonResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| nextLink | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| values | [ [SitesData](#sitesdata) ] |  | No |

#### SitesDataResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| content | string | The remark. The element is not used for this API and responded with “null” by default. | No |
| nextToken | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| results | [ [SitesData](#sitesdata) ] |  | No |

#### StringJobResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| jobId | string |  | No |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |

#### StringJsonResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| nextLink | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| values | [ string ] |  | No |

#### SummaryViewModuleOptions

Get summary by using the paging option

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| language | string | Sets the language of the report you are about to export.  <value>Default: en-US Support: en-US/ja-JP/fr-FR</value> | No |
| startPage | integer | Sets the start page from which you want to get the group summary. The default value is 1. | No |
| pageSize | integer | Sets the number of groups displayed in each page of the result. The number must be no larger than 100. The default value is 100. | No |

#### UserSummaryViewModule

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| displayName | string | The display name of the user. | No |
| loginName | string | The login name of the user. | No |
| email | string | The email address of the user. | No |
| userStatus | string | The user’s sign-in status in Microsoft 365.  <value>  Blocked (for a user in Azure AD whose sign-in to Microsoft 365 is blocked)  Activate (for a user in Azure AD whose sign in to Microsoft 365 is active)  Not in Azure AD (for a user who is not in Azure AD)  </value> | No |
| trustStatus | string | The user’s trust status in Insights for Microsoft 365.  <value>  Trusted (for a trusted user in Insights for Microsoft 365)  Not Trusted (for a user who is not trusted in Insights for Microsoft 365)  </value> | No |
| sitesWithDirectAcccess | integer | The number of sensitive items to which the user has been granted direct permissions. | No |
| lastSignIn | string | The user’s last sign-in time to Microsoft 365. | No |
| createdOn | dateTime | The time when the user is created in Azure AD. | No |

#### UserSummaryViewModuleJsonResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| nextLink | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| values | [ [UserSummaryViewModule](#usersummaryviewmodule) ] |  | No |

#### UserSummaryViewModuleResultList

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | integer | The HTTP response status code. | No |
| message | string | The error message. | No |
| content | string | The remark. The element is not used for this API and responded with “null” by default. | No |
| nextToken | string | The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default. | No |
| results | [ [UserSummaryViewModule](#usersummaryviewmodule) ] |  | No |