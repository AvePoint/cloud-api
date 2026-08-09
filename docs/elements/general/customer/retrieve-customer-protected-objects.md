# Retrieve Customer Protected Objects

Use this API to retrieve customer's protected objects of Cloud Backup for Microsoft 365.

## Permissions

The following permission is required to call the API.  
You must register an app through Elements > API app registration to authenticate and authorize your access to Elements API. For details, refer to [App Registration](../../register-app.md). 

| API | Permission |
|-----------|--------|
| `/partner/external/v3/general/customers/{customerId}/m365/backup/modules/{module}/protected-objects` | elements.cbprotected.read.all |

## Request

This section outlines the details of the HTTP method and endpoint used to get protected objects for a customer.

| Method | Endpoint | Description |
|---|---|---|
| GET | `/partner/external/v3/general/customers/{customerId}/m365/backup/modules/{module}/protected-objects` | Retrieves customer's protected objects of Cloud Backup for Microsoft 365. |

## URL Parameters

This section outlines the parameters required to specify which customer and module you want to retrieve.

| Parameter | Description | Type | Required |
|---|---|---|---|
| customerId | The ID of the customer. | string | Yes |
| module | The value of the backup module. <ul><li>**0** - Exchange Online mailboxes</li><li>**1** - SharePoint Online</li><li>**2** - OneDrive</li><li>**3** - Microsoft 365 Groups</li><li>**4** - Project Online</li><li>**5** - Exchange Online Public Folders</li><li>**6** - Microsoft Teams</li><li>**9** - Viva Engage</li><li>**10** - Microsoft Teams chat</li><li>**11** - Power BI</li><li>**12** - Power Automate</li><li>**14** - Power Apps</li><li>**15** - Copilot Studio Agents</li></ul>| integer| Yes |
| pageSize | The page index for range paging. (1, 1000) | integer | Yes |
| skipToken | The next page token. | string | No |

## Response

If the request has been successfully processed, a 200 OK response will be returned along with a paged collection in the response body.

| Field | Description | Type |
|---|---|---|
| data | The information of the protected objects returned by the API. | `List<ProtectedObject>` |
| metadata.skipToken | The page size used for the result. | string |
| metadata.totalCount | The total number of protected objects. | integer |


**Protected Object Information**

| Field | Description | Type |
|---|---|---|
|displayName|The display name or email of the protected object.|string|
|mailboxType|The type of mailbox. <ul><li> User Mailbox</li><li> Resource Mailbox</li><li> In-Place Archive Mailbox</li><li> Shared Mailbox</li><li> Public Folder</li><li> Recoverable Items Folder</li></ul>|string?|
|containerName| The name of the container in the AOS scan profile.|string|
|tenantId|The ID of the Microsoft 365 tenant.|string|
|size|The size (bytes) of the protected object in the Microsoft 365 tenant.|long|

## Request Sample for the SharePoint Online Sites module

To use this API, send a GET request to one of the supported endpoints.

```http
GET https://graph-us.avepointonlineservices.com/partner/external/v3/general/customers/552d9fe5-****-****-****-704a499037f8/m365/backup/modules/1/protected-objects?pageSize=1
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

```json
{
  "data": [
    {
      "displayName": "https://7cnp3r.sharepoint.com/sites/Nopermission5", // The display name of the protected object
      "mailboxType": "", // The type of mailbox
      "containerName": "Default SharePoint Site Container", // The name of the container in the AOS scan profile
      "tenantId": "7a08aa01-****-****-****-e77cfc3f5f7d", // The ID of the Microsoft 365 tenant
      "size": 31861095 // The size (bytes) of the protected object in the Microsoft 365 tenant
    },
    ...
  ],
  "metadata": {
    "skipToken": "4GIMAVngRri1ua0Kz2Tpjc8flbzJBsxikoRQHGYc5N7druLZYdlbGtKKgg==", // The page size used for the result
    "totalCount": 1 // The total number of protected objects
  }
}
```

## Request Sample for the Exchange Online Mailboxes Module

To use this API, send a GET request to one of the supported endpoints.

```http
GET https://graph-us.avepointonlineservices.com/partner/external/v3/general/customers/552d9fe5-****-****-****-704a499037f8/m365/backup/modules/0/protected-objects?pageSize=1&skipToken=veXFMV+oaRDCrXqSfJDOjnD3PKk8vQQzZCn2UutLFepsy30zc3JTK8gbtw==
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body.

```json
{
    "data": [
        {
            "displayName": "sophia_equipmentMailbox@7cnp3r.onmicrosoft.com(Resource Mailbox)", // The email of the protected object
            "mailboxType": "Resource Mailbox", // The type of mailbox
            "containerName": "Default Exchange Mailbox Container", // The name of the container in the AOS scan profile
            "tenantId": "7a08aa01-****-****-****-e77cfc3f5f7d", // The ID of the Microsoft 365 tenant
            "size": 4444266 // The size (bytes) of the protected object in the Microsoft 365 tenant
        }
    ],
    "metadata": {
        "skipToken": "W4hoOmj2XZvar5Ir7+CVg3IYgo3eL9kUtd7JZtmF4FYLdd0grwanhaLnrg==", // The page size used for the result
        "totalCount": 1 // The total number of protected objects
    }
}
```
