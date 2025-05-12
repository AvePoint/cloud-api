# Graph API for Insights

> Version v2

An ASP.NET Core Graph API for Insights

## Path Table

| Method | Path | Description |
| --- | --- | --- |
| GET | [/activities/object/{path}/export](#getactivitiesobjectpathexport) | Get object activity |
| GET | [/groups/summary](#getgroupssummary) | Gets the summary of specific groups. |
| GET | [/groups/{groupId}/access/export](#getgroupsgroupidaccessexport) | Gets the .zip file from exporting the permission related information of specific groups. |
| GET | [/Healthz](#gethealthz) | The API is for check health of API service |
| GET | [/job/{jobId}/exportstatus](#getjobjobidexportstatus) | Get Activity export job statuts |
| GET | [/job/{jobId}/exportfile](#getjobjobidexportfile) | Download Activity export  file |
| GET | [/sharingLinks/{siteUrl}/summary](#getsharinglinkssiteurlsummary) | Gets the summary of specific links. |
| GET | [/sharingLinks/export](#getsharinglinksexport) | Gets the .zip file from exporting the permission related information of specific links. |
| GET | [/sites/permission](#getsitespermission) | Gets the permission-related information of specific site collections. |
| GET | [/sites/permission/export](#getsitespermissionexport) | Exports the permission reports of specific site collections. |
| GET | [/sites/overview](#getsitesoverview) | Get sites data |
| GET | [/sites/{siteUrl}/siteid](#getsitessiteurlsiteid) |  |
| GET | [/sites/{siteId}/detailrecords](#getsitessiteiddetailrecords) |  |
| GET | [/users/summary](#getuserssummary) | Gets the summary of specific users. |
| GET | [/users/access](#getusersaccess) | Gets the permission-related information of specific users. |
| GET | [/users/{email}/access/export](#getusersemailaccessexport) | Exports the access reports of specific users in different workspaces. |
| GET | [/users/{email}/activities/export](#getusersemailactivitiesexport) | get user activity |

## Reference Table

| Name | Path | Description |
| --- | --- | --- |
| AccessViewModule | [#/components/schemas/AccessViewModule](#componentsschemasaccessviewmodule) |  |
| AccessViewModuleJsonResultList | [#/components/schemas/AccessViewModuleJsonResultList](#componentsschemasaccessviewmodulejsonresultlist) |  |
| AccessViewModuleOptions | [#/components/schemas/AccessViewModuleOptions](#componentsschemasaccessviewmoduleoptions) | Get access report by using the paging option |
| AccessViewModuleResultList | [#/components/schemas/AccessViewModuleResultList](#componentsschemasaccessviewmoduleresultlist) |  |
| ActivityExportOptions | [#/components/schemas/ActivityExportOptions](#componentsschemasactivityexportoptions) | Activity export  Options |
| DetailRecordData | [#/components/schemas/DetailRecordData](#componentsschemasdetailrecorddata) |  |
| DetailRecordDataJsonResultList | [#/components/schemas/DetailRecordDataJsonResultList](#componentsschemasdetailrecorddatajsonresultlist) |  |
| DetailRecordDataResultList | [#/components/schemas/DetailRecordDataResultList](#componentsschemasdetailrecorddataresultlist) |  |
| DetailRecordExportOptions | [#/components/schemas/DetailRecordExportOptions](#componentsschemasdetailrecordexportoptions) |  |
| ExportOptionType | [#/components/schemas/ExportOptionType](#componentsschemasexportoptiontype) |  |
| ExportOptions | [#/components/schemas/ExportOptions](#componentsschemasexportoptions) | Export job option |
| ExportOptionsBase | [#/components/schemas/ExportOptionsBase](#componentsschemasexportoptionsbase) |  |
| ExportResult | [#/components/schemas/ExportResult](#componentsschemasexportresult) | Export Job Result |
| Filter | [#/components/schemas/Filter](#componentsschemasfilter) |  |
| GroupSummaryViewModule | [#/components/schemas/GroupSummaryViewModule](#componentsschemasgroupsummaryviewmodule) |  |
| GroupSummaryViewModuleJsonResultList | [#/components/schemas/GroupSummaryViewModuleJsonResultList](#componentsschemasgroupsummaryviewmodulejsonresultlist) |  |
| GroupSummaryViewModuleResultList | [#/components/schemas/GroupSummaryViewModuleResultList](#componentsschemasgroupsummaryviewmoduleresultlist) |  |
| InsightsExportResult | [#/components/schemas/InsightsExportResult](#componentsschemasinsightsexportresult) | Insights Export Job Result |
| Int32JobStatusResultList | [#/components/schemas/Int32JobStatusResultList](#componentsschemasint32jobstatusresultlist) |  |
| LinkViewModule | [#/components/schemas/LinkViewModule](#componentsschemaslinkviewmodule) |  |
| LinkViewModuleJsonResultList | [#/components/schemas/LinkViewModuleJsonResultList](#componentsschemaslinkviewmodulejsonresultlist) |  |
| LinkViewModuleOptions | [#/components/schemas/LinkViewModuleOptions](#componentsschemaslinkviewmoduleoptions) | Get links by using the paging option |
| LinkViewModuleResultList | [#/components/schemas/LinkViewModuleResultList](#componentsschemaslinkviewmoduleresultlist) |  |
| PrincipalTypes | [#/components/schemas/PrincipalTypes](#componentsschemasprincipaltypes) |  |
| SitePermissionViewModule | [#/components/schemas/SitePermissionViewModule](#componentsschemassitepermissionviewmodule) |  |
| SitePermissionViewModuleJsonResultList | [#/components/schemas/SitePermissionViewModuleJsonResultList](#componentsschemassitepermissionviewmodulejsonresultlist) |  |
| SitePermissionViewModuleOptions | [#/components/schemas/SitePermissionViewModuleOptions](#componentsschemassitepermissionviewmoduleoptions) | Export permission report by using the paging option
/// |
| SitePermissionViewModuleResultList | [#/components/schemas/SitePermissionViewModuleResultList](#componentsschemassitepermissionviewmoduleresultlist) |  |
| SiteResponseViewModel | [#/components/schemas/SiteResponseViewModel](#componentsschemassiteresponseviewmodel) |  |
| SiteResponseViewModelResultList | [#/components/schemas/SiteResponseViewModelResultList](#componentsschemassiteresponseviewmodelresultlist) |  |
| SiteUrlRequest | [#/components/schemas/SiteUrlRequest](#componentsschemassiteurlrequest) |  |
| SitesData | [#/components/schemas/SitesData](#componentsschemassitesdata) |  |
| SitesDataJsonResultList | [#/components/schemas/SitesDataJsonResultList](#componentsschemassitesdatajsonresultlist) |  |
| SitesDataResultList | [#/components/schemas/SitesDataResultList](#componentsschemassitesdataresultlist) |  |
| StringJobResultList | [#/components/schemas/StringJobResultList](#componentsschemasstringjobresultlist) |  |
| StringJsonResultList | [#/components/schemas/StringJsonResultList](#componentsschemasstringjsonresultlist) |  |
| SummaryViewModuleOptions | [#/components/schemas/SummaryViewModuleOptions](#componentsschemassummaryviewmoduleoptions) | Get summary by using the paging option |
| UserSummaryViewModule | [#/components/schemas/UserSummaryViewModule](#componentsschemasusersummaryviewmodule) |  |
| UserSummaryViewModuleJsonResultList | [#/components/schemas/UserSummaryViewModuleJsonResultList](#componentsschemasusersummaryviewmodulejsonresultlist) |  |
| UserSummaryViewModuleResultList | [#/components/schemas/UserSummaryViewModuleResultList](#componentsschemasusersummaryviewmoduleresultlist) |  |
| BearerAuth | [#/components/securitySchemes/BearerAuth](#componentssecurityschemesbearerauth) | JWT Authorization header using the Bearer scheme. |
| BearerAuth1 | [#/components/securitySchemes/BearerAuth1](#componentssecurityschemesbearerauth1) | JWT Authorization header using the Bearer scheme. |

## Path Details

***

### [GET]/activities/object/{path}/export

- Summary  
Get object activity

#### Parameters(Query)

```ts
startTime?: string
```

```ts
finishTime?: string
```

```ts
eventTypes?: string[]
```

#### Responses

- 200 OK

`text/plain`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`application/json`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`text/json`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

***

### [GET]/groups/summary

- Summary  
Gets the summary of specific groups.

#### Parameters(Query)

```ts
startPage?: integer
```

```ts
pageSize?: integer
```

#### Responses

- 200 OK

`text/plain`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The group name.
    displayName?: string
    // The group ID.
    groupId?: string
    // The email address of the group
    email?: string
    // The type of the group.
    // <value>
    // Microsoft 365 Group
    // Security Group
    // Distribution Group
    // Mail-enabled Security Group
    // </value>
    groupType?: string
    // The membership type of the group:
    // <value>
    // Assigned
    // Dynamic
    // </value>
    membershipType?: string
    // The time when the group is created.
    createdOn?: string
    // The number of external users in the group.
    externalMemberCount?: integer
  }[]
}
```

`application/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The group name.
    displayName?: string
    // The group ID.
    groupId?: string
    // The email address of the group
    email?: string
    // The type of the group.
    // <value>
    // Microsoft 365 Group
    // Security Group
    // Distribution Group
    // Mail-enabled Security Group
    // </value>
    groupType?: string
    // The membership type of the group:
    // <value>
    // Assigned
    // Dynamic
    // </value>
    membershipType?: string
    // The time when the group is created.
    createdOn?: string
    // The number of external users in the group.
    externalMemberCount?: integer
  }[]
}
```

`text/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The group name.
    displayName?: string
    // The group ID.
    groupId?: string
    // The email address of the group
    email?: string
    // The type of the group.
    // <value>
    // Microsoft 365 Group
    // Security Group
    // Distribution Group
    // Mail-enabled Security Group
    // </value>
    groupType?: string
    // The membership type of the group:
    // <value>
    // Assigned
    // Dynamic
    // </value>
    membershipType?: string
    // The time when the group is created.
    createdOn?: string
    // The number of external users in the group.
    externalMemberCount?: integer
  }[]
}
```

***

### [GET]/groups/{groupId}/access/export

- Summary  
Gets the .zip file from exporting the permission related information of specific groups.

#### Parameters(Query)

```ts
exportOptionType?: enum[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

```ts
siteUrls?: string[]
```

```ts
dataSources?: string[]
```

#### Responses

- 200 OK

`text/plain`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`application/json`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`text/json`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

***

### [GET]/Healthz

- Summary  
The API is for check health of API service

- Description  
GET: /healthz

#### Responses

- 200 OK

`text/plain`

```ts
{
  "type": "string"
}
```

`application/json`

```ts
{
  "type": "string"
}
```

`text/json`

```ts
{
  "type": "string"
}
```

***

### [GET]/job/{jobId}/exportstatus

- Summary  
Get Activity export job statuts

#### Responses

- 200 OK

`text/plain`

```ts
{
  jobStatus?: integer
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`application/json`

```ts
{
  jobStatus?: integer
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`text/json`

```ts
{
  jobStatus?: integer
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

***

### [GET]/job/{jobId}/exportfile

- Summary  
Download Activity export  file

#### Responses

- 200 OK

***

### [GET]/sharingLinks/{siteUrl}/summary

- Summary  
Gets the summary of specific links.

#### Parameters(Query)

```ts
linkType?: integer
```

```ts
pageSize?: integer
```

```ts
nextLink?: string
```

#### Responses

- 200 OK

`text/plain`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The ID in the link summary.
    id?: string
    // The site ID in which the object is shared by the link.
    siteId?: string
    // The selfID of the object which is shared by the link.
    selfId?: string
    // The link ID.
    linkId?: string
    // The link login name.
    logonName?: string
    // The time when the link is created.
    createTime?: string
    // The time when the link is expired.
    // This is only available for anonymous links.
    expireTime?: string
    // The object name that is shared via the link.
    name?: string
    // The object URL that is shared via the link.
    objectUrl?: string
    // The link type.
    // <value>
    // 32(for flexible link)
    // 64 (for organization link)
    // 128 (for anonymous link)
    // </value>
    linkType?: string
    // The user who created the link.
    shareBy?: string
    // The parent from which the permission inherits.
    inheritFrom?: string
    // The status whether the permission is inherited.
    inheritType?: string
    // The number of users and groups with whom the link is shared.
    shareWith?: integer
    // The link URL.
    linkUrl?: string
    // The permission with which the link is shared.
    permission?: string
    // The type of the object shared via the link.
    fileType?: string
    // The sensitivity level of the object shared via the link.
    sensitivityLevel?: string
  }[]
}
```

`application/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The ID in the link summary.
    id?: string
    // The site ID in which the object is shared by the link.
    siteId?: string
    // The selfID of the object which is shared by the link.
    selfId?: string
    // The link ID.
    linkId?: string
    // The link login name.
    logonName?: string
    // The time when the link is created.
    createTime?: string
    // The time when the link is expired.
    // This is only available for anonymous links.
    expireTime?: string
    // The object name that is shared via the link.
    name?: string
    // The object URL that is shared via the link.
    objectUrl?: string
    // The link type.
    // <value>
    // 32(for flexible link)
    // 64 (for organization link)
    // 128 (for anonymous link)
    // </value>
    linkType?: string
    // The user who created the link.
    shareBy?: string
    // The parent from which the permission inherits.
    inheritFrom?: string
    // The status whether the permission is inherited.
    inheritType?: string
    // The number of users and groups with whom the link is shared.
    shareWith?: integer
    // The link URL.
    linkUrl?: string
    // The permission with which the link is shared.
    permission?: string
    // The type of the object shared via the link.
    fileType?: string
    // The sensitivity level of the object shared via the link.
    sensitivityLevel?: string
  }[]
}
```

`text/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The ID in the link summary.
    id?: string
    // The site ID in which the object is shared by the link.
    siteId?: string
    // The selfID of the object which is shared by the link.
    selfId?: string
    // The link ID.
    linkId?: string
    // The link login name.
    logonName?: string
    // The time when the link is created.
    createTime?: string
    // The time when the link is expired.
    // This is only available for anonymous links.
    expireTime?: string
    // The object name that is shared via the link.
    name?: string
    // The object URL that is shared via the link.
    objectUrl?: string
    // The link type.
    // <value>
    // 32(for flexible link)
    // 64 (for organization link)
    // 128 (for anonymous link)
    // </value>
    linkType?: string
    // The user who created the link.
    shareBy?: string
    // The parent from which the permission inherits.
    inheritFrom?: string
    // The status whether the permission is inherited.
    inheritType?: string
    // The number of users and groups with whom the link is shared.
    shareWith?: integer
    // The link URL.
    linkUrl?: string
    // The permission with which the link is shared.
    permission?: string
    // The type of the object shared via the link.
    fileType?: string
    // The sensitivity level of the object shared via the link.
    sensitivityLevel?: string
  }[]
}
```

***

### [GET]/sharingLinks/export

- Summary  
Gets the .zip file from exporting the permission related information of specific links.

#### Parameters(Query)

```ts
exportLinkType?: enum[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 16, 32, 41, 64, 65, 128, 201, 301, 302, 303, 304, 305, 306, 307, 308, 309, 310, 311, 312, 313, 314, 315, 316, 317, 318, 319, 320, 333, 401, 402, 403]
```

```ts
startTime?: string
```

```ts
finishTime?: string
```

#### Responses

- 200 OK

`text/plain`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`application/json`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`text/json`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

***

### [GET]/sites/permission

- Summary  
Gets the permission-related information of specific site collections.

- Description  
The api/v1/site/permission/export API is recommended when the site collections that you are about to export are over 2,000.

#### Parameters(Query)

```ts
siteUrls?: string[]
```

```ts
pageSize?: integer
```

```ts
nextLink?: string
```

#### Responses

- 200 OK

`text/plain`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The data source.
    module?: string
    // The name of the permission.
    name?: string
    // The URL of the object.
    url?: string
    // The object type.
    objectType?: string
    // The name of the user or group.
    principalName?: string
    // Email
    email?: string
    // The type of the user or group.
    principalType?: string
    // The permission.
    permission?: string
    // The number of members in the group.
    numberOfMembers?: integer
    // The status whether external users exist.
    isExternalUser?: boolean
    // The status whether the permission is inherited.
    inheritType?: string
    // The members that are given the permission via link.
    linkGivingAccessTo?: string
  }[]
}
```

`application/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The data source.
    module?: string
    // The name of the permission.
    name?: string
    // The URL of the object.
    url?: string
    // The object type.
    objectType?: string
    // The name of the user or group.
    principalName?: string
    // Email
    email?: string
    // The type of the user or group.
    principalType?: string
    // The permission.
    permission?: string
    // The number of members in the group.
    numberOfMembers?: integer
    // The status whether external users exist.
    isExternalUser?: boolean
    // The status whether the permission is inherited.
    inheritType?: string
    // The members that are given the permission via link.
    linkGivingAccessTo?: string
  }[]
}
```

`text/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The data source.
    module?: string
    // The name of the permission.
    name?: string
    // The URL of the object.
    url?: string
    // The object type.
    objectType?: string
    // The name of the user or group.
    principalName?: string
    // Email
    email?: string
    // The type of the user or group.
    principalType?: string
    // The permission.
    permission?: string
    // The number of members in the group.
    numberOfMembers?: integer
    // The status whether external users exist.
    isExternalUser?: boolean
    // The status whether the permission is inherited.
    inheritType?: string
    // The members that are given the permission via link.
    linkGivingAccessTo?: string
  }[]
}
```

***

### [GET]/sites/permission/export

- Summary  
Exports the permission reports of specific site collections.

- Description  
You can only export permission reports of 100 site collections at a time.

#### Parameters(Query)

```ts
siteUrls?: string[]
```

#### Responses

- 200 OK

`text/plain`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`application/json`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`text/json`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

***

### [GET]/sites/overview

- Summary  
Get sites data

#### Parameters(Query)

```ts
riskLevel?: integer[]
```

```ts
nextLink?: string
```

#### Responses

- 200 OK

`text/plain`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    siteName?: string
    siteUrl?: string
    riskItemCount?: integer
    sensitiveItemCount?: integer
    exposureItemCount?: integer
  }[]
}
```

`application/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    siteName?: string
    siteUrl?: string
    riskItemCount?: integer
    sensitiveItemCount?: integer
    exposureItemCount?: integer
  }[]
}
```

`text/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    siteName?: string
    siteUrl?: string
    riskItemCount?: integer
    sensitiveItemCount?: integer
    exposureItemCount?: integer
  }[]
}
```

***

### [GET]/sites/{siteUrl}/siteid

#### Responses

- 200 OK

`text/plain`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values?: string[]
}
```

`application/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values?: string[]
}
```

`text/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values?: string[]
}
```

***

### [GET]/sites/{siteId}/detailrecords

#### Parameters(Query)

```ts
nextLink?: string
```

#### Responses

- 200 OK

`text/plain`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    id?: string
    name?: string
    location?: string
    objectType?: string
    createdBy?: string
    module?: string
    inheritType?: string
    siteName?: string
    sensitivityLevel?: string
    exposureLevel?: string
    scannedTime?: string
    createdTime?: string
    modifiedTime?: string
    channelName?: string
    riskLevel?: string
    privacy?: string
    sensitiveInfoType?: string[]
    sensitivityLabel?: string
    tagName?: string
    retentionLabel?: string
    creatorEmail?: string
  }[]
}
```

`application/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    id?: string
    name?: string
    location?: string
    objectType?: string
    createdBy?: string
    module?: string
    inheritType?: string
    siteName?: string
    sensitivityLevel?: string
    exposureLevel?: string
    scannedTime?: string
    createdTime?: string
    modifiedTime?: string
    channelName?: string
    riskLevel?: string
    privacy?: string
    sensitiveInfoType?: string[]
    sensitivityLabel?: string
    tagName?: string
    retentionLabel?: string
    creatorEmail?: string
  }[]
}
```

`text/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    id?: string
    name?: string
    location?: string
    objectType?: string
    createdBy?: string
    module?: string
    inheritType?: string
    siteName?: string
    sensitivityLevel?: string
    exposureLevel?: string
    scannedTime?: string
    createdTime?: string
    modifiedTime?: string
    channelName?: string
    riskLevel?: string
    privacy?: string
    sensitiveInfoType?: string[]
    sensitivityLabel?: string
    tagName?: string
    retentionLabel?: string
    creatorEmail?: string
  }[]
}
```

***

### [GET]/users/summary

- Summary  
Gets the summary of specific users.

#### Parameters(Query)

```ts
startPage?: integer
```

```ts
pageSize?: integer
```

#### Responses

- 200 OK

`text/plain`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The display name of the user.
    displayName?: string
    // The login name of the user.
    loginName?: string
    // The email address of the user.
    email?: string
    // The user’s sign-in status in Microsoft 365.
    // <value>
    // Blocked (for a user in Azure AD whose sign-in to Microsoft 365 is blocked)
    // Activate (for a user in Azure AD whose sign in to Microsoft 365 is active)
    // Not in Azure AD (for a user who is not in Azure AD)
    // </value>
    userStatus?: string
    // The user’s trust status in Insights for Microsoft 365.
    // <value>
    // Trusted (for a trusted user in Insights for Microsoft 365)
    // Not Trusted (for a user who is not trusted in Insights for Microsoft 365)
    // </value>
    trustStatus?: string
    // The number of sensitive items to which the user has been granted direct permissions.
    sitesWithDirectAcccess?: integer
    // The user’s last sign-in time to Microsoft 365.
    lastSignIn?: string
    // The time when the user is created in Azure AD.
    createdOn?: string
  }[]
}
```

`application/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The display name of the user.
    displayName?: string
    // The login name of the user.
    loginName?: string
    // The email address of the user.
    email?: string
    // The user’s sign-in status in Microsoft 365.
    // <value>
    // Blocked (for a user in Azure AD whose sign-in to Microsoft 365 is blocked)
    // Activate (for a user in Azure AD whose sign in to Microsoft 365 is active)
    // Not in Azure AD (for a user who is not in Azure AD)
    // </value>
    userStatus?: string
    // The user’s trust status in Insights for Microsoft 365.
    // <value>
    // Trusted (for a trusted user in Insights for Microsoft 365)
    // Not Trusted (for a user who is not trusted in Insights for Microsoft 365)
    // </value>
    trustStatus?: string
    // The number of sensitive items to which the user has been granted direct permissions.
    sitesWithDirectAcccess?: integer
    // The user’s last sign-in time to Microsoft 365.
    lastSignIn?: string
    // The time when the user is created in Azure AD.
    createdOn?: string
  }[]
}
```

`text/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The display name of the user.
    displayName?: string
    // The login name of the user.
    loginName?: string
    // The email address of the user.
    email?: string
    // The user’s sign-in status in Microsoft 365.
    // <value>
    // Blocked (for a user in Azure AD whose sign-in to Microsoft 365 is blocked)
    // Activate (for a user in Azure AD whose sign in to Microsoft 365 is active)
    // Not in Azure AD (for a user who is not in Azure AD)
    // </value>
    userStatus?: string
    // The user’s trust status in Insights for Microsoft 365.
    // <value>
    // Trusted (for a trusted user in Insights for Microsoft 365)
    // Not Trusted (for a user who is not trusted in Insights for Microsoft 365)
    // </value>
    trustStatus?: string
    // The number of sensitive items to which the user has been granted direct permissions.
    sitesWithDirectAcccess?: integer
    // The user’s last sign-in time to Microsoft 365.
    lastSignIn?: string
    // The time when the user is created in Azure AD.
    createdOn?: string
  }[]
}
```

***

### [GET]/users/access

- Summary  
Gets the permission-related information of specific users.

- Description  
The api/v1/user/permission/export API is recommended when the users that you are about to export are over 2,000.

#### Parameters(Query)

```ts
siteUrls?: string[]
```

```ts
emails?: string[]
```

```ts
nextLink?: string
```

#### Responses

- 200 OK

`text/plain`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The data source.
    module?: string
    // The name of the site.
    siteName?: string
    // The name of the permission.
    name?: string
    // The URL of the object.
    location?: string
    // The object type.
    objectType?: string
    // The status whether the permission is inherited.
    inheritType?: string
    // The permission.
    permission?: string
    // The sensitivity level of the object.
    sensitivityLevel?: string
    // The sensitive info type of the object.
    sensitiveInfoType?: string
    // The status whether the permission is directly granted.
    isDirect?: boolean
    // The sensitivity label of the object.
    sensitivityLabel?: string
    // The parent from which the permission inherits.
    inheritedFrom?: string
  }[]
}
```

`application/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The data source.
    module?: string
    // The name of the site.
    siteName?: string
    // The name of the permission.
    name?: string
    // The URL of the object.
    location?: string
    // The object type.
    objectType?: string
    // The status whether the permission is inherited.
    inheritType?: string
    // The permission.
    permission?: string
    // The sensitivity level of the object.
    sensitivityLevel?: string
    // The sensitive info type of the object.
    sensitiveInfoType?: string
    // The status whether the permission is directly granted.
    isDirect?: boolean
    // The sensitivity label of the object.
    sensitivityLabel?: string
    // The parent from which the permission inherits.
    inheritedFrom?: string
  }[]
}
```

`text/json`

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The data source.
    module?: string
    // The name of the site.
    siteName?: string
    // The name of the permission.
    name?: string
    // The URL of the object.
    location?: string
    // The object type.
    objectType?: string
    // The status whether the permission is inherited.
    inheritType?: string
    // The permission.
    permission?: string
    // The sensitivity level of the object.
    sensitivityLevel?: string
    // The sensitive info type of the object.
    sensitiveInfoType?: string
    // The status whether the permission is directly granted.
    isDirect?: boolean
    // The sensitivity label of the object.
    sensitivityLabel?: string
    // The parent from which the permission inherits.
    inheritedFrom?: string
  }[]
}
```

***

### [GET]/users/{email}/access/export

- Summary  
Exports the access reports of specific users in different workspaces.

#### Parameters(Query)

```ts
siteUrls?: string[]
```

```ts
dataSources?: string[]
```

#### Responses

- 200 OK

`text/plain`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`application/json`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`text/json`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

***

### [GET]/users/{email}/activities/export

- Summary  
get user activity

#### Parameters(Query)

```ts
startTime?: string
```

```ts
finishTime?: string
```

```ts
eventTypes?: string[]
```

#### Responses

- 200 OK

`text/plain`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`application/json`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

`text/json`

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

## References

### #/components/schemas/AccessViewModule

```ts
{
  // The data source.
  module?: string
  // The name of the site.
  siteName?: string
  // The name of the permission.
  name?: string
  // The URL of the object.
  location?: string
  // The object type.
  objectType?: string
  // The status whether the permission is inherited.
  inheritType?: string
  // The permission.
  permission?: string
  // The sensitivity level of the object.
  sensitivityLevel?: string
  // The sensitive info type of the object.
  sensitiveInfoType?: string
  // The status whether the permission is directly granted.
  isDirect?: boolean
  // The sensitivity label of the object.
  sensitivityLabel?: string
  // The parent from which the permission inherits.
  inheritedFrom?: string
}
```

### #/components/schemas/AccessViewModuleJsonResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The data source.
    module?: string
    // The name of the site.
    siteName?: string
    // The name of the permission.
    name?: string
    // The URL of the object.
    location?: string
    // The object type.
    objectType?: string
    // The status whether the permission is inherited.
    inheritType?: string
    // The permission.
    permission?: string
    // The sensitivity level of the object.
    sensitivityLevel?: string
    // The sensitive info type of the object.
    sensitiveInfoType?: string
    // The status whether the permission is directly granted.
    isDirect?: boolean
    // The sensitivity label of the object.
    sensitivityLabel?: string
    // The parent from which the permission inherits.
    inheritedFrom?: string
  }[]
}
```

### #/components/schemas/AccessViewModuleOptions

```ts
// Get access report by using the paging option
{
  // Sets the language of the report you are about to export.
  // <value>Default: en-US Support: en-US/ja-JP/fr-FR</value>
  language?: string
  siteUrls?: string[]
  emails?: string[]
  // Sets whether to get the remaining results of a request of which the results are more than 100.
  token?: string
  // Sets the number of results for one page. 100 results on one page at most.
  top?: integer
}
```

### #/components/schemas/AccessViewModuleResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The remark. The element is not used for this API and responded with “null” by default.
  content?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextToken?: string
  results: {
    // The data source.
    module?: string
    // The name of the site.
    siteName?: string
    // The name of the permission.
    name?: string
    // The URL of the object.
    location?: string
    // The object type.
    objectType?: string
    // The status whether the permission is inherited.
    inheritType?: string
    // The permission.
    permission?: string
    // The sensitivity level of the object.
    sensitivityLevel?: string
    // The sensitive info type of the object.
    sensitiveInfoType?: string
    // The status whether the permission is directly granted.
    isDirect?: boolean
    // The sensitivity label of the object.
    sensitivityLabel?: string
    // The parent from which the permission inherits.
    inheritedFrom?: string
  }[]
}
```

### #/components/schemas/ActivityExportOptions

```ts
// Activity export  Options
{
  // Sets the language of the report you are about to export.
  // <value>Default: en-US Support: en-US/ja-JP/fr-FR</value>
  language?: string
  // Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss"
  startTime?: string
  // Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss"
  endTime?: string
  eventTypes?: string[]
  // Filter by Path
  path?: string
  // Filter by User email
  email?: string
}
```

### #/components/schemas/DetailRecordData

```ts
{
  id?: string
  name?: string
  location?: string
  objectType?: string
  createdBy?: string
  module?: string
  inheritType?: string
  siteName?: string
  sensitivityLevel?: string
  exposureLevel?: string
  scannedTime?: string
  createdTime?: string
  modifiedTime?: string
  channelName?: string
  riskLevel?: string
  privacy?: string
  sensitiveInfoType?: string[]
  sensitivityLabel?: string
  tagName?: string
  retentionLabel?: string
  creatorEmail?: string
}
```

### #/components/schemas/DetailRecordDataJsonResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    id?: string
    name?: string
    location?: string
    objectType?: string
    createdBy?: string
    module?: string
    inheritType?: string
    siteName?: string
    sensitivityLevel?: string
    exposureLevel?: string
    scannedTime?: string
    createdTime?: string
    modifiedTime?: string
    channelName?: string
    riskLevel?: string
    privacy?: string
    sensitiveInfoType?: string[]
    sensitivityLabel?: string
    tagName?: string
    retentionLabel?: string
    creatorEmail?: string
  }[]
}
```

### #/components/schemas/DetailRecordDataResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The remark. The element is not used for this API and responded with “null” by default.
  content?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextToken?: string
  results: {
    id?: string
    name?: string
    location?: string
    objectType?: string
    createdBy?: string
    module?: string
    inheritType?: string
    siteName?: string
    sensitivityLevel?: string
    exposureLevel?: string
    scannedTime?: string
    createdTime?: string
    modifiedTime?: string
    channelName?: string
    riskLevel?: string
    privacy?: string
    sensitiveInfoType?: string[]
    sensitivityLabel?: string
    tagName?: string
    retentionLabel?: string
    creatorEmail?: string
  }[]
}
```

### #/components/schemas/DetailRecordExportOptions

```ts
{
  token?: string
  pageSize?: integer
  filters: {
    id?: string
    values?: string[]
  }[]
  language?: string
  siteId?: string
}
```

### #/components/schemas/ExportOptionType

```ts
{
  "enum": [
    0,
    1,
    2,
    3,
    4,
    5,
    6,
    7,
    8,
    9
  ],
  "type": "integer",
  "format": "int32"
}
```

### #/components/schemas/ExportOptions

```ts
// Export job option
{
  // Sets the language of the report you are about to export.
  // <value>Default: en-US Support: en-US/ja-JP/fr-FR</value>
  language?: string
  siteUrls?: string[]
  emails?: string[]
  dataSources?: string[]
  exportOptionType?: enum[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
  exportLinkType?: enum[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 16, 32, 41, 64, 65, 128, 201, 301, 302, 303, 304, 305, 306, 307, 308, 309, 310, 311, 312, 313, 314, 315, 316, 317, 318, 319, 320, 333, 401, 402, 403]
  // Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss"
  startTime?: string
  // Filter By Time, Time format:yyyy-MM-ddTHH:mm:ss"
  endTime?: string
}
```

### #/components/schemas/ExportOptionsBase

```ts
{
  token?: string
  pageSize?: integer
  filters: {
    id?: string
    values?: string[]
  }[]
}
```

### #/components/schemas/ExportResult

```ts
// Export Job Result
{
  // Download file request Uri
  getFileUrl?: string
  // Export Job Id
  id?: integer
}
```

### #/components/schemas/Filter

```ts
{
  id?: string
  values?: string[]
}
```

### #/components/schemas/GroupSummaryViewModule

```ts
{
  // The group name.
  displayName?: string
  // The group ID.
  groupId?: string
  // The email address of the group
  email?: string
  // The type of the group.
  // <value>
  // Microsoft 365 Group
  // Security Group
  // Distribution Group
  // Mail-enabled Security Group
  // </value>
  groupType?: string
  // The membership type of the group:
  // <value>
  // Assigned
  // Dynamic
  // </value>
  membershipType?: string
  // The time when the group is created.
  createdOn?: string
  // The number of external users in the group.
  externalMemberCount?: integer
}
```

### #/components/schemas/GroupSummaryViewModuleJsonResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The group name.
    displayName?: string
    // The group ID.
    groupId?: string
    // The email address of the group
    email?: string
    // The type of the group.
    // <value>
    // Microsoft 365 Group
    // Security Group
    // Distribution Group
    // Mail-enabled Security Group
    // </value>
    groupType?: string
    // The membership type of the group:
    // <value>
    // Assigned
    // Dynamic
    // </value>
    membershipType?: string
    // The time when the group is created.
    createdOn?: string
    // The number of external users in the group.
    externalMemberCount?: integer
  }[]
}
```

### #/components/schemas/GroupSummaryViewModuleResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The remark. The element is not used for this API and responded with “null” by default.
  content?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextToken?: string
  results: {
    // The group name.
    displayName?: string
    // The group ID.
    groupId?: string
    // The email address of the group
    email?: string
    // The type of the group.
    // <value>
    // Microsoft 365 Group
    // Security Group
    // Distribution Group
    // Mail-enabled Security Group
    // </value>
    groupType?: string
    // The membership type of the group:
    // <value>
    // Assigned
    // Dynamic
    // </value>
    membershipType?: string
    // The time when the group is created.
    createdOn?: string
    // The number of external users in the group.
    externalMemberCount?: integer
  }[]
}
```

### #/components/schemas/InsightsExportResult

```ts
// Insights Export Job Result
{
  // Export Status
  // <value>
  // None = 0,
  // Inprogress = 1,
  // Successful = 2,
  // Failed = 3,
  // SuccessWithException = 4,
  // Stopping = 5,
  // Stopped = 6
  // </value>
  status?: integer
  // Status Text
  description?: string
}
```

### #/components/schemas/Int32JobStatusResultList

```ts
{
  jobStatus?: integer
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

### #/components/schemas/LinkViewModule

```ts
{
  // The ID in the link summary.
  id?: string
  // The site ID in which the object is shared by the link.
  siteId?: string
  // The selfID of the object which is shared by the link.
  selfId?: string
  // The link ID.
  linkId?: string
  // The link login name.
  logonName?: string
  // The time when the link is created.
  createTime?: string
  // The time when the link is expired.
  // This is only available for anonymous links.
  expireTime?: string
  // The object name that is shared via the link.
  name?: string
  // The object URL that is shared via the link.
  objectUrl?: string
  // The link type.
  // <value>
  // 32(for flexible link)
  // 64 (for organization link)
  // 128 (for anonymous link)
  // </value>
  linkType?: string
  // The user who created the link.
  shareBy?: string
  // The parent from which the permission inherits.
  inheritFrom?: string
  // The status whether the permission is inherited.
  inheritType?: string
  // The number of users and groups with whom the link is shared.
  shareWith?: integer
  // The link URL.
  linkUrl?: string
  // The permission with which the link is shared.
  permission?: string
  // The type of the object shared via the link.
  fileType?: string
  // The sensitivity level of the object shared via the link.
  sensitivityLevel?: string
}
```

### #/components/schemas/LinkViewModuleJsonResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The ID in the link summary.
    id?: string
    // The site ID in which the object is shared by the link.
    siteId?: string
    // The selfID of the object which is shared by the link.
    selfId?: string
    // The link ID.
    linkId?: string
    // The link login name.
    logonName?: string
    // The time when the link is created.
    createTime?: string
    // The time when the link is expired.
    // This is only available for anonymous links.
    expireTime?: string
    // The object name that is shared via the link.
    name?: string
    // The object URL that is shared via the link.
    objectUrl?: string
    // The link type.
    // <value>
    // 32(for flexible link)
    // 64 (for organization link)
    // 128 (for anonymous link)
    // </value>
    linkType?: string
    // The user who created the link.
    shareBy?: string
    // The parent from which the permission inherits.
    inheritFrom?: string
    // The status whether the permission is inherited.
    inheritType?: string
    // The number of users and groups with whom the link is shared.
    shareWith?: integer
    // The link URL.
    linkUrl?: string
    // The permission with which the link is shared.
    permission?: string
    // The type of the object shared via the link.
    fileType?: string
    // The sensitivity level of the object shared via the link.
    sensitivityLevel?: string
  }[]
}
```

### #/components/schemas/LinkViewModuleOptions

```ts
// Get links by using the paging option
{
  // Sets the language of the report you are about to export.
  // <value>Default: en-US Support: en-US/ja-JP/fr-FR</value>
  language?: string
  siteUrls?: string[]
  // Sets whether to get the remaining results of a request of which the results are more than 100.
  token?: string
  // Sets the number of links displayed in each page of the result. The number must be no larger than 100.
  pageSize?: integer
  //  Sets the link types that you are about to get.
  //  <value>
  // External Link = 32
  // Organization Link = 64
  // Anonymous Link = 128
  // </value>
  linkType?: integer
}
```

### #/components/schemas/LinkViewModuleResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The remark. The element is not used for this API and responded with “null” by default.
  content?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextToken?: string
  results: {
    // The ID in the link summary.
    id?: string
    // The site ID in which the object is shared by the link.
    siteId?: string
    // The selfID of the object which is shared by the link.
    selfId?: string
    // The link ID.
    linkId?: string
    // The link login name.
    logonName?: string
    // The time when the link is created.
    createTime?: string
    // The time when the link is expired.
    // This is only available for anonymous links.
    expireTime?: string
    // The object name that is shared via the link.
    name?: string
    // The object URL that is shared via the link.
    objectUrl?: string
    // The link type.
    // <value>
    // 32(for flexible link)
    // 64 (for organization link)
    // 128 (for anonymous link)
    // </value>
    linkType?: string
    // The user who created the link.
    shareBy?: string
    // The parent from which the permission inherits.
    inheritFrom?: string
    // The status whether the permission is inherited.
    inheritType?: string
    // The number of users and groups with whom the link is shared.
    shareWith?: integer
    // The link URL.
    linkUrl?: string
    // The permission with which the link is shared.
    permission?: string
    // The type of the object shared via the link.
    fileType?: string
    // The sensitivity level of the object shared via the link.
    sensitivityLevel?: string
  }[]
}
```

### #/components/schemas/PrincipalTypes

```ts
{
  "enum": [
    0,
    1,
    2,
    3,
    4,
    5,
    6,
    7,
    8,
    9,
    10,
    11,
    12,
    16,
    32,
    41,
    64,
    65,
    128,
    201,
    301,
    302,
    303,
    304,
    305,
    306,
    307,
    308,
    309,
    310,
    311,
    312,
    313,
    314,
    315,
    316,
    317,
    318,
    319,
    320,
    333,
    401,
    402,
    403
  ],
  "type": "integer",
  "format": "int32"
}
```

### #/components/schemas/SitePermissionViewModule

```ts
{
  // The data source.
  module?: string
  // The name of the permission.
  name?: string
  // The URL of the object.
  url?: string
  // The object type.
  objectType?: string
  // The name of the user or group.
  principalName?: string
  // Email
  email?: string
  // The type of the user or group.
  principalType?: string
  // The permission.
  permission?: string
  // The number of members in the group.
  numberOfMembers?: integer
  // The status whether external users exist.
  isExternalUser?: boolean
  // The status whether the permission is inherited.
  inheritType?: string
  // The members that are given the permission via link.
  linkGivingAccessTo?: string
}
```

### #/components/schemas/SitePermissionViewModuleJsonResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The data source.
    module?: string
    // The name of the permission.
    name?: string
    // The URL of the object.
    url?: string
    // The object type.
    objectType?: string
    // The name of the user or group.
    principalName?: string
    // Email
    email?: string
    // The type of the user or group.
    principalType?: string
    // The permission.
    permission?: string
    // The number of members in the group.
    numberOfMembers?: integer
    // The status whether external users exist.
    isExternalUser?: boolean
    // The status whether the permission is inherited.
    inheritType?: string
    // The members that are given the permission via link.
    linkGivingAccessTo?: string
  }[]
}
```

### #/components/schemas/SitePermissionViewModuleOptions

```ts
// Export permission report by using the paging option
// ///
{
  // Sets the language of the report you are about to export.
  // <value>Default: en-US Support: en-US/ja-JP/fr-FR</value>
  language?: string
  siteUrls?: string[]
  // Sets whether to get the remaining results of a request of which the results are more than 100.
  token?: string
  // Sets the number of results for one page. 100 results on one page at most.
  top?: integer
}
```

### #/components/schemas/SitePermissionViewModuleResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The remark. The element is not used for this API and responded with “null” by default.
  content?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextToken?: string
  results: {
    // The data source.
    module?: string
    // The name of the permission.
    name?: string
    // The URL of the object.
    url?: string
    // The object type.
    objectType?: string
    // The name of the user or group.
    principalName?: string
    // Email
    email?: string
    // The type of the user or group.
    principalType?: string
    // The permission.
    permission?: string
    // The number of members in the group.
    numberOfMembers?: integer
    // The status whether external users exist.
    isExternalUser?: boolean
    // The status whether the permission is inherited.
    inheritType?: string
    // The members that are given the permission via link.
    linkGivingAccessTo?: string
  }[]
}
```

### #/components/schemas/SiteResponseViewModel

```ts
{
  siteId?: string
  siteUrl?: string
}
```

### #/components/schemas/SiteResponseViewModelResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The remark. The element is not used for this API and responded with “null” by default.
  content?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextToken?: string
  results: {
    siteId?: string
    siteUrl?: string
  }[]
}
```

### #/components/schemas/SiteUrlRequest

```ts
{
  siteUrls?: string[]
}
```

### #/components/schemas/SitesData

```ts
{
  siteName?: string
  siteUrl?: string
  riskItemCount?: integer
  sensitiveItemCount?: integer
  exposureItemCount?: integer
}
```

### #/components/schemas/SitesDataJsonResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    siteName?: string
    siteUrl?: string
    riskItemCount?: integer
    sensitiveItemCount?: integer
    exposureItemCount?: integer
  }[]
}
```

### #/components/schemas/SitesDataResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The remark. The element is not used for this API and responded with “null” by default.
  content?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextToken?: string
  results: {
    siteName?: string
    siteUrl?: string
    riskItemCount?: integer
    sensitiveItemCount?: integer
    exposureItemCount?: integer
  }[]
}
```

### #/components/schemas/StringJobResultList

```ts
{
  jobId?: string
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
}
```

### #/components/schemas/StringJsonResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values?: string[]
}
```

### #/components/schemas/SummaryViewModuleOptions

```ts
// Get summary by using the paging option
{
  // Sets the language of the report you are about to export.
  // <value>Default: en-US Support: en-US/ja-JP/fr-FR</value>
  language?: string
  // Sets the start page from which you want to get the group summary. The default value is 1.
  startPage?: integer
  // Sets the number of groups displayed in each page of the result. The number must be no larger than 100. The default value is 100.
  pageSize?: integer
}
```

### #/components/schemas/UserSummaryViewModule

```ts
{
  // The display name of the user.
  displayName?: string
  // The login name of the user.
  loginName?: string
  // The email address of the user.
  email?: string
  // The user’s sign-in status in Microsoft 365.
  // <value>
  // Blocked (for a user in Azure AD whose sign-in to Microsoft 365 is blocked)
  // Activate (for a user in Azure AD whose sign in to Microsoft 365 is active)
  // Not in Azure AD (for a user who is not in Azure AD)
  // </value>
  userStatus?: string
  // The user’s trust status in Insights for Microsoft 365.
  // <value>
  // Trusted (for a trusted user in Insights for Microsoft 365)
  // Not Trusted (for a user who is not trusted in Insights for Microsoft 365)
  // </value>
  trustStatus?: string
  // The number of sensitive items to which the user has been granted direct permissions.
  sitesWithDirectAcccess?: integer
  // The user’s last sign-in time to Microsoft 365.
  lastSignIn?: string
  // The time when the user is created in Azure AD.
  createdOn?: string
}
```

### #/components/schemas/UserSummaryViewModuleJsonResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextLink?: string
  values: {
    // The display name of the user.
    displayName?: string
    // The login name of the user.
    loginName?: string
    // The email address of the user.
    email?: string
    // The user’s sign-in status in Microsoft 365.
    // <value>
    // Blocked (for a user in Azure AD whose sign-in to Microsoft 365 is blocked)
    // Activate (for a user in Azure AD whose sign in to Microsoft 365 is active)
    // Not in Azure AD (for a user who is not in Azure AD)
    // </value>
    userStatus?: string
    // The user’s trust status in Insights for Microsoft 365.
    // <value>
    // Trusted (for a trusted user in Insights for Microsoft 365)
    // Not Trusted (for a user who is not trusted in Insights for Microsoft 365)
    // </value>
    trustStatus?: string
    // The number of sensitive items to which the user has been granted direct permissions.
    sitesWithDirectAcccess?: integer
    // The user’s last sign-in time to Microsoft 365.
    lastSignIn?: string
    // The time when the user is created in Azure AD.
    createdOn?: string
  }[]
}
```

### #/components/schemas/UserSummaryViewModuleResultList

```ts
{
  // The HTTP response status code.
  status?: integer
  // The error message.
  message?: string
  // The remark. The element is not used for this API and responded with “null” by default.
  content?: string
  // The token to be used to get the remaining results of this request. The element is not used for this API and responded with “null” by default.
  nextToken?: string
  results: {
    // The display name of the user.
    displayName?: string
    // The login name of the user.
    loginName?: string
    // The email address of the user.
    email?: string
    // The user’s sign-in status in Microsoft 365.
    // <value>
    // Blocked (for a user in Azure AD whose sign-in to Microsoft 365 is blocked)
    // Activate (for a user in Azure AD whose sign in to Microsoft 365 is active)
    // Not in Azure AD (for a user who is not in Azure AD)
    // </value>
    userStatus?: string
    // The user’s trust status in Insights for Microsoft 365.
    // <value>
    // Trusted (for a trusted user in Insights for Microsoft 365)
    // Not Trusted (for a user who is not trusted in Insights for Microsoft 365)
    // </value>
    trustStatus?: string
    // The number of sensitive items to which the user has been granted direct permissions.
    sitesWithDirectAcccess?: integer
    // The user’s last sign-in time to Microsoft 365.
    lastSignIn?: string
    // The time when the user is created in Azure AD.
    createdOn?: string
  }[]
}
```

### #/components/securitySchemes/BearerAuth

```ts
{
  "type": "apiKey",
  "description": "JWT Authorization header using the Bearer scheme.",
  "name": "Authorization",
  "in": "header"
}
```

### #/components/securitySchemes/BearerAuth1

```ts
{
  "type": "apiKey",
  "description": "JWT Authorization header using the Bearer scheme.",
  "name": "Authorization",
  "in": "header"
}
```