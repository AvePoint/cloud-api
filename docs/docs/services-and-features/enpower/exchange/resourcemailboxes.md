# Retrieve Resource Mailbox Details

Use this API to access and retrieve information of your resource mailboxes.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/exchange/resourcemailboxes` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your resource mailboxes.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/exchange/resourcemailboxes` | Retrieves your shared mailboxes' information | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of resource mailbox records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of resource mailboxes are retrieved. By default, data of all tenants are retrieved. | string | No |
| resourceMailboxType | The type of resource mailboxes to retrieve. <br> Valid values: <br> <ul><li> **0** for **Both** <br> </li><li> **1** for **Room** <br> </li><li> **2** for **Equipment**.</ul> By default, both types of resource mailboxes are retrieved.| enum | No |

## Responses

The API response provides detailed information about the resource mailboxes retrieved. Each resource mailbox in the response includes various attributes that describe its properties and status.

| **Elements**           | Description                                                           | Type   | 
|--------------------|-----------------------------------------------------------------------|--------|
| resourceMailboxes             | A list containing resource mailboxes with detailed information. For the detailed list of responses, refer to [Resource Mailbox Details](#resource-mailbox-details).             | list  | 
| totalCount      | Total number of resource mailboxes retrieved.                   | integer    | 
| nextLink | Reference to the next page of results | string |


### Resource Mailbox Details

| **Elements**                              | Description                                                                 | Type    |
|---------------------------------------|-----------------------------------------------------------------------------|---------|
| Id                                    | The unique identifier of the resource mailbox in PowerShell.                              | string  |
| userId                                | The unique identifier of the resource mailbox in Microsoft 365.          | string  |
| principalName                         | The user principal name of the resource mailbox.                            | string  |
| name                                  | The name of the resource.                                                   | string  |
| emailAddress                          | The email address of the resource mailbox.                                  | string  |
| displayName                           | The display name of the resource.                                           | string  |
| recipientType                         | The recipient type of the resource mailbox.                                 | string  |
| status                                | The status of the resource mailbox.                                         | string  |
| hiddenFromAddressListsEnabled         | Indicates whether this mailbox is hidden from the address list. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| createTime                            | The time when the resource was created.                                     | string  |
| modifiedTime                          | The latest time when the resource was modified.                             | string  |
| tenantId                              | The unique identifier of the tenant that the resource belongs to.           | string  |
| tenantDomain                          | The domain of the tenant that the resource belongs to.                      | string  |
| container                             | The container that the resource is in.                                      | string  |
| containerId                           | The unique identifier of the container that the resource is in.             | string  |
| itemCount                             | The number of items in the resource mailbox.                                | integer |
| storageUsed                           | The used storage size of the resource mailbox.                              | integer |
| issueWarningQuota                     | The maximum storage limit before a warning is issued. If the mailbox size reaches or exceeds the value specified, Exchange sends a warning message to the user. | integer |
| prohibitSendQuota                     | The prohibit send limit for the mailbox. If the mailbox size reaches or exceeds the specified limit, Exchange prevents the user from sending new messages and displays a descriptive error message. | integer |
| prohibitSendReceiveQuota              | The prohibit send and receive limit for the mailbox. If the mailbox size reaches or exceeds the specified limit, Exchange prevents the mailbox user from sending new messages and won't deliver any new messages to the mailbox. Any messages sent to the mailbox are returned to the sender with a descriptive error message. | integer |
| deletedItemCount                      | The number of items in the Deleted items folder of the resource mailbox.     | integer |
| deletedItemSize                       | The size of Deleted items folder of the resource mailbox.                   | integer |
| firstScanTime                         | The time when the resource was initially scanned into EnPower.              | string  |
| officeLocation                        | The office location of the resource.                                        | string  |
| businessPhones                        | The business phone number of the resource.                                  | string  |
| department                            | The department of the resource.                                             | string  |
| companyName                           | The company name of the resource.                                           | string  |
| streetAddress                         | The street address of the resource.                                         | string  |
| city                                  | The city of the resource.                                                   | string  |
| state                                 | The state of the resource.                                                  | string  |
| postalCode                            | The postal code of the resource.                                            | string  |
| countryOrRegion                       | The country or region of the resource.                                      | string  |
| resourceCapacity                      | The capacity of the resource.                                               | integer |
| addressBookPolicy                     | The address book policy of the resource mailbox.                            | string  |
| customAttributes                      | Extension attributes added to the resource mailbox. For the detailed list of the custom attributes, refer to [Custom Attribute Details](#custom-attribute-details). | object  |
| notes                                 | The notes added to the resource.                                            | string  |
| primaryContact                        | The Cloud Governance primary contact of the resource mailbox. For the detailed user properties, refer to [User Details](#user-details). | object  |
| secondaryContact                      | The Cloud Governance secondary contact of the resource mailbox. For the detailed user properties, refer to [User Details](#user-details). | object  |
| lastRenewalTime                       | The last time when the resource mailbox was renewed.                        | string  |
| lastRenewalBy                         | The latest user who renewed the resource mailbox. For the detailed user properties, refer to [User Details](#user-details). | object  |
| renewProfileApplied                   | Indicates if a renewal profile has been applied to the resource mailbox. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| metadata                              | The Cloud Governance metadata associated with the resource mailbox. For the detailed metadata properties, refer to [Cloud Governance Metadata Details](#cloud-governance-metadata-details). | list    |
| electionProfileApplied                | Indicates if a contact election profile has been applied to the resource mailbox. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| isRegistered                          | Indicates if the resource mailbox has been imported to Cloud Governance. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| phase                                 | The current phase of the resource mailbox in Cloud Governance.              | string  |
| phaseAssignees                        | The individuals assigned to the current phase of the resource mailbox in Cloud Governance. For the detailed user properties, refer to [User Details](#user-details). | string  |
| renewProfile                          | The Cloud Governance renewal profile applied to the resource mailbox. For the detailed profile properties, refer to [Cloud Governance Profile Details](#cloud-governance-profile-details). | string  |
| electionProfile                       | The Cloud Governance contact election profile applied to the resource mailbox. For the detailed profile properties, refer to [Cloud Governance Profile Details](#cloud-governance-profile-details). | string  |
| claimStatus                           | The Cloud Governance claim status of the resource mailbox.                  | string  |



### Custom Attribute Details

| Elements          | Description                                              | Type    |
|-------------------|----------------------------------------------------------|---------|
| customAttribute1  | The value of custom attribute 1 added to the resource mailbox. | string  |
| customAttribute2  | The value of custom attribute 2 added to the resource mailbox. | string  |
| customAttribute3  | The value of custom attribute 3 added to the resource mailbox. | string  |
| customAttribute4  | The value of custom attribute 4 added to the resource mailbox. | string  |
| customAttribute5  | The value of custom attribute 5 added to the resource mailbox. | string  |
| customAttribute6  | The value of custom attribute 6 added to the resource mailbox. | string  |
| customAttribute7  | The value of custom attribute 7 added to the resource mailbox. | string  |
| customAttribute8  | The value of custom attribute 8 added to the resource mailbox. | string  |
| customAttribute9  | The value of custom attribute 9 added to the resource mailbox. | string  |
| customAttribute10 | The value of custom attribute 10 added to the resource mailbox. | string  |
| customAttribute11 | The value of custom attribute 11 added to the resource mailbox. | string  |
| customAttribute12 | The value of custom attribute 12 added to the resource mailbox. | string  |
| customAttribute13 | The value of custom attribute 13 added to the resource mailbox. | string  |
| customAttribute14 | The value of custom attribute 14 added to the resource mailbox. | string  |
| customAttribute15 | The value of custom attribute 15 added to the resource mailbox. | string  |


### User Details

| Elements             | Description                                      | Type    |
|----------------------|--------------------------------------------------|---------|
| id                   | The unique identifier for the user.              | string  |
| displayName          | The display name associated with the user.       | string  |
| email                | The email address associated with the user.      | string  |
| tenantId             | The unique identifier for the tenant where the user is hosted. | string  |
| userPrincipalName    | The user principal name of the user.             | string  |
| objectId             | The unique object ID for the user.               | string  |
| jobTitle             | The job title associated with the user.          | string  |
| department           | The department associated with the user.         | string  |
| companyName          | The company name associated with the user.       | string  |
| office               | The office location associated with the user.    | string  |
| city                 | The city associated with the user.               | string  |
| countryOrRegion      | The country or region associated with the user.  | string  |


### Cloud Governance Metadata Details

| Elements             | Description                                      | Type    |
|----------------------|--------------------------------------------------|---------|
| metadataType         | The type of metadata. <br> Valid values: <br> <ul><li> **0** for none <br> </li><li> **1** for single line of text <br></li><li> **2** for multiple lines of text <br></li><li> **3** for yes/no <br></li><li> **4** for choice <br></li><li> **5** for people picker filter profile <br></li><li> **6** for managed metadata <br></li><li> **7** for hyperlink <br></li><li> **8** for user profile property <br></li><li> **9** for Microsoft Entra property <br></li><li> **10** for lookup </li></ul> | integer |
| value                | The metadata value.                              | object  |
| id                   | The unique identifier for the metadata.          | string  |
| name                 | The metadata name.                               | string  |
| metadataSetting      | The custom metadata.                             | object  |


### Cloud Governance Profile Details

| Elements             | Description                                      | Type    |
|----------------------|--------------------------------------------------|---------|
| id                   | The unique identifier for the profile.           | string  |
| name                 | The name for the profile.                        | string  |


## Request Sample

To use this API, send a GET request to the specified endpoint, including necessary parameters as defined in the references. This will return the relevant object details in a structured format, enabling easy integration with other systems or applications. The following request is an API call to the EnPower environment in the US - East region.

```json
https://graph-us.avepointonlineservices.com/smp/exchange/resourcemailboxes
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).

```json
{
    "resourceMailboxes": [
        {
            "id": "73669ae7-55fe-4b47-8fc4-47324c01d5d2",//The unique identifier of the resource mailbox in PowerShell
            "userId": "",// The unique identifier of the resource mailbox in Microsoft 365
            "principalName": "",// The user principal name of the resource mailbox
            "name": "",// The name of the resource mailbox in PowerShell
            "emailAddress": "",// The email address of the resource mailbox
            "displayName": "Annie_Room_BulkCreate_008",// The display name of the resource
            "recipientType": "Room mailbox", // The recipient type of the resource mailbox
            "status": "Normal", // The status of the resource mailbox.
            "hiddenFromAddressListsEnabled": false, // Indicates whether this mailbox is hidden from the address list
            "createTime": "2025-01-13 02:32:52", // The time when the resource was created
            "modifiedTime": "2025-01-22 23:26:10", // The latest time when the resource was modified
            "tenantId": "",// The unique identifier of the tenant that the resource belongs to
            "tenantDomain": "", // The domain of the tenant that the resource belongs to
            "container": "Default Exchange mailbox container",// The container that the resource is in
            "containerId": "", // The unique identifier of the container that the resource is in
            "itemCount": 56, // The number of items in the resource mailbox
            "storageUsed": 0,// The used storage size of the resource mailbox
            "issueWarningQuota": 0, // The maximum storage limit before a warning is issued. If the mailbox size reaches or exceeds the value specified, Exchange sends a warning message to the user
            "prohibitSendQuota": 0, // The prohibit send limit for the mailbox. If the mailbox size reaches or exceeds the specified limit, Exchange prevents the user from sending new messages and displays a descriptive error message 
            "prohibitSendReceiveQuota": 0, // The prohibit send and receive limit for the mailbox. If the mailbox size reaches or exceeds the specified limit, Exchange prevents the mailbox user from sending new messages and won't deliver any new messages to the mailbox. Any messages sent to the mailbox are returned to the sender with a descriptive error message
            "deletedItemCount": 0, // The number of items in the Deleted items folder of the resource mailbox
            "deletedItemSize": 0, // The size of Deleted items folder of the resource mailbox
            "firstScanTime": "2025-01-13 02:35:03",// The time when the resource was initially scanned into EnPower
            "officeLocation": "Ho Chi Minh",// The office location of the resource
            "businessPhones": "[\"809189220\"]",// The business phone number of the resource
            "department": "QA01",// The department of the resource
            "companyName": "Facebook",// The company name of the resource
            "streetAddress": "Nguyen Van Linh",// The street address of the resource
            "city": "Ho Chi Minh",// The city of the resource
            "state": "",// The state of the resource
            "postalCode": "",// The postal code of the resource
            "countryOrRegion": "",// The country or region of the resource
            "resourceCapacity": 9999,// The capacity of the resource
            "addressBookPolicy": null,// The address book policy of the resource mailbox
            "customAttributes": {//Custom Attributes // Extension attributes added to the resource mailbox
                "customAttribute1": "", // The value of custom attribute 1 added to the resource mailbox
                "customAttribute2": "", // The value of custom attribute 2 added to the resource mailbox
                "customAttribute3": "", // The value of custom attribute 3 added to the resource mailbox
                "customAttribute4": "", // The value of custom attribute 4 added to the resource mailbox
                "customAttribute5": "", // The value of custom attribute 5 added to the resource mailbox
                "customAttribute6": "", // The value of custom attribute 6 added to the resource mailbox
                "customAttribute7": "", // The value of custom attribute 7 added to the resource mailbox
                "customAttribute8": "", // The value of custom attribute 8 added to the resource mailbox
                "customAttribute9": "", // The value of custom attribute 9 added to the resource mailbox
                "customAttribute10": "", // The value of custom attribute 10 added to the resource mailbox
                "customAttribute11": "", // The value of custom attribute 11 added to the resource mailbox
                "customAttribute12": "", // The value of custom attribute 12 added to the resource mailbox
                "customAttribute13": "", // The value of custom attribute 13 added to the resource mailbox
                "customAttribute14": "", // The value of custom attribute 14 added to the resource mailbox
                "customAttribute15": "" // The value of custom attribute 15 added to the resource mailbox
            },
            "notes": "", // The notes added to the resource
            "primaryContact": null, // The Cloud Governance primary contact of the resource mailbox
            "secondaryContact": null,// The Cloud Governance secondary contact of the resource mailbox
            "lastRenewalTime": "",// The last time when the resource mailbox was renewed.
            "lastRenewalBy": null,// The latest user who renewed the resource mailbox
            "renewProfileApplied": null,// Indicates if a renewal profile has been applied to the resource mailbox
            "metadata": [],// The Cloud Governance metadata associated with the resource mailbox
            "electionProfileApplied": null,// Indicates if a contact election profile has been applied to the resource mailbox
            "isRegistered": false,// Indicates if the resource mailbox has been imported to Cloud Governance
            "phase": "",// The current phase of the resource mailbox in Cloud Governance
            "phaseAssignees": "",// The individuals assigned to the current phase of the resource mailbox in Cloud Governance
            "renewProfile": "N/A", // The Cloud Governance renewal profile applied to the resource mailbox
            "electionProfile": "N/A",// The Cloud Governance contact election profile applied to the resource mailbox
            "claimStatus": ""// The Cloud Governance claim status of the resource mailbox
        }
    ],
    "totalCount": 1,
    "nextLink": ""
}
