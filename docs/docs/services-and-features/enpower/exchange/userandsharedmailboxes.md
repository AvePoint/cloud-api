# Retrieve User or Shared Mailbox Details

Use this API to access and retrieve information of your user or shared mailboxes.

## Permission

The following permission is required to call the API.
You must register the app through AvePoint Online Services > App registrations to authenticate and authorize your access to AvePoint Graph API.
For details, refer to [Authentication and Authorization](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#authentication-and-authorization).

| API   | Permission |
|-------------------|---------------|
|`/smp/exchange/mailboxes` | enpower.data.read.all | 

## Request

This section provides details on the HTTP method and endpoint used to retrieve general information of your user or shared mailboxes.

| Method | Endpoint | Description | 
|--- | --- | --- |
| GET | `/smp/exchange/mailboxes` | Retrieves your user or shared mailboxes' information | 

## Query Parameters

The API supports several query parameters to refine and customize the data retrieval process.

| Parameters | Description | Type | Required |
|--- | --- | --- | --- |
| top | The number of resource mailbox records retrieved and returned each page. The default number is 100. You can enter a number from 1 to 1000. | integer | No |
| tenant | The tenant in which data of resource mailboxes are retrieved. By default, data of all tenants are retrieved. | string | No |
| resourceMailboxType | The type of resource mailboxes to retrieve. <br> Valid values: <br> <ul><li> **0** for **Both** <br> </li><li> **1** for **User mailbox** <br> </li><li> **2** for **Shared mailbox**.</ul> By default, both types of mailboxes are retrieved.| enum | No |

## Responses

The API response provides detailed information about the mailboxes retrieved. Each mailbox in the response includes various attributes that describe its properties and status.

| Elements           | Description                                                           | Type   | 
|--------------------|-----------------------------------------------------------------------|--------|
| mailboxes             | A list containing user or shared mailboxes with detailed information. For the detailed list of responses, refer to [Mailbox Details](#mailbox-details).             | list  | 
| totalCount      | Total number of mailboxes retrieved.                   | integer    | 
| nextLink | Reference to the next page of results | string |

### Mailbox Details

| Elements                              | Description                                                                 | Type    |
|---------------------------------------|-----------------------------------------------------------------------------|---------|
| Id                                    | The unique identifier of the mailbox in PowerShell.                                       | string  |
| userId                                | The unique identifier of the mailbox in Microsoft 365.                   | string  |
| principalName                         | The user principal name of the mailbox.                                     | string  |
| name                                  | The name of the mailbox in PowerShell.                                                    | string  |
| emailAddress                          | The email address of the mailbox.                                           | string  |
| displayName                           | The display name of the mailbox.                                            | string  |
| recipientType                         | The recipient type of the mailbox.                                          | string  |
| status                                | The status of the mailbox.                                                  | string  |
| hiddenFromAddressListsEnabled         | Indicates whether this mailbox is hidden from the address list. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| createTime                            | The time when the mailbox was created.                                      | string  |
| modifiedTime                          | The latest time when the mailbox was modified.                              | string  |
| tenantId                              | The unique identifier of the tenant that the mailbox belongs to.            | string  |
| tenantDomain                          | The domain of the tenant that the mailbox belongs to.                       | string  |
| container                             | The container that the mailbox is in.                                       | string  |
| containerId                           | The unique identifier of the container that the mailbox is in.              | string  |
| itemCount                             | The number of items in the mailbox.                                         | integer |
| storageUsed                           | The used storage size of the mailbox.                                       | integer |
| issueWarningQuota                     | The maximum storage limit before a warning is issued. If the mailbox size reaches or exceeds the value specified, Exchange sends a warning message to the user. | integer |
| prohibitSendQuota                     | The prohibit send limit for the mailbox. If the mailbox size reaches or exceeds the specified limit, Exchange prevents the user from sending new messages and displays a descriptive error message. | integer |
| prohibitSendReceiveQuota              | The prohibit send and receive limit for the mailbox. If the mailbox size reaches or exceeds the specified limit, Exchange prevents the mailbox user from sending new messages and won't deliver any new messages to the mailbox. Any messages sent to the mailbox are returned to the sender with a descriptive error message. | integer |
| deletedItemCount                      | The number of items in the Deleted items folder of the mailbox.             | integer |
| deletedItemSize                       | The size of Deleted items folder of the mailbox.                            | integer |
| firstScanTime                         | The time when the mailbox was initially scanned into EnPower.               | string  |
| firstName                             | The first name of the mailbox user.                                         | string  |
| lastName                              | The last name of the mailbox user.                                          | string  |
| alias                                 | The alias of the mailbox.                                                   | string  |
| autoReplyEnabled                      | Indicates whether this mailbox has automatic replies enabled. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| litigationHoldEnabled                 | Indicates whether this mailbox has litigation hold enabled. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| emailForwardingEnabled                | Indicates whether this mailbox has email forwarding enabled. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| archiveStatus                         | The archiving status of the mailbox.                                        | string  |
| archiveName                           | The name of the folder in the user's mailbox that contains the archive.     | string  |
| lastActivityDate                      | The latest date when the mailbox has any activity.                          | string  |
| forwardingAddressDomain               | The domain of the email address that emails are being forwarded to.         | string  |
| externalForwardingAddressDomain       | The domain of the external email address that emails are being forwarded to.| string  |
| externalEmailForwardingEnabled        | Indicates whether this mailbox is forwarding emails to external email addresses. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| recipientLimits                       | The maximum number of allowed recipients on the To, Cc, and Bcc lines of the email message sent from this mailbox. | integer |
| mailboxPolicies                       | The mailbox policies applied to this mailbox. For the list of mailbox policies, refer to [Mailbox Policy Details](#mailbox-policy-details). | object  |
| primaryContact                        | The Cloud Governance primary contact of the mailbox. For the detailed user properties, refer to [User Details](#user-details). | object  |
| secondaryContact                      | The Cloud Governance secondary contact of the mailbox. For the detailed user properties, refer to [User Details](#user-details). | object  |
| lastRenewalTime                       | The last time when the mailbox was renewed.                                 | string  |
| lastRenewalBy                         | The latest user who renewed the mailbox. For the detailed user properties, refer to [User Details](#user-details). | object  |
| renewProfileApplied                   | Indicates if a renewal profile has been applied to the mailbox. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| metadata                              | The Cloud Governance metadata associated with the mailbox. For the detailed metadata properties, refer to [Cloud Governance Metadata Details](#cloud-governance-metadata-details). | list    |
| electionProfileApplied                | Indicates if a contact election profile has been applied to the mailbox. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| isRegistered                          | Indicates if the mailbox has been imported to Cloud Governance. <br> Valid values: <br> <ul><li> **true** for yes <br> </li><li> **false** for no <br> | boolean |
| phase                                 | The current phase of the mailbox in Cloud Governance.                       | string  |
| phaseAssignees                        | The individuals assigned to the current phase of the mailbox in Cloud Governance. For the detailed user properties, refer to [User Details](#user-details). | string  |
| renewProfile                          | The Cloud Governance renewal profile applied to the mailbox. For the detailed profile properties, refer to [Cloud Governance Profile Details](#cloud-governance-profile-details). | string  |
| electionProfile                       | The Cloud Governance contact election profile applied to the mailbox. For the detailed profile properties, refer to [Cloud Governance Profile Details](#cloud-governance-profile-details). | string  |
| claimStatus                           | The Cloud Governance claim status of the mailbox.                           | string  |


### Mailbox Policy Details

| Elements              | Description                                      | Type    |
|-----------------------|--------------------------------------------------|---------|
| addressBookPolicy     | The address book policy applied to the mailbox.  | string  |
| retentionPolicy       | The retention policy applied to the mailbox.     | string  |
| roleAssignmentPolicy  | The role assignment policy applied to the mailbox. | string  |
| sharingPolicy         | The sharing policy applied to the mailbox.       | string  |


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
https://graph-us.avepointonlineservices.com/smp/exchange/mailboxes
```

## Response Sample

If the request has been successfully processed, a 200 OK response will be returned along with the requested information displayed in the response body. For more details on the HTTP status code, refer to [HTTP Status Code](https://learn.avepoint.com/docs/Use-AvePoint-Graph-Modern-API.html#http-status-code).

```json
{
    "mailboxes": [
        {
            "id": "f78625f8-3ec3-4665-835a-3502484af738", // The unique identifier of the mailbox
            "userId": "",// The unique identifier of the mailbox in Microsft 365
            "principalName": "", // The user principal name of the mailbox
            "name": "",// The name of the mailbox in PowerShell.
            "emailAddress": "", // The email address of the mailbox.
            "displayName": "39_Gary_aa_the", // The display name of the mailbox
            "recipientType": "User mailbox", // The recipient type of the mailbox
            "status": "Archived", // The status of the mailbox
            "hiddenFromAddressListsEnabled": false, Indicates whether this mailbox is hidden from the address list
            "createTime": "2024-10-02 06:27:18", // The time when the mailbox was created
            "modifiedTime": "2024-12-08 17:25:26",// The latest time when the mailbox was modified
            "tenantId": "",// The unique identifier of the tenant that the mailbox belongs to
            "tenantDomain": "", // The domain of the tenant that the mailbox belongs to
            "container": "Default Exchange mailbox container",// The container that the mailbox is in
            "containerId": "", // The unique identifier of the container that the mailbox is in
            "itemCount": 56, // The number of items in the mailbox
            "storageUsed": 1,// The used storage size of the mailbox
            "issueWarningQuota": 100352, // The maximum storage limit before a warning is issued. If the mailbox size reaches or exceeds the value specified, Exchange sends a warning message to the user
            "prohibitSendQuota": 101376,// The prohibit send limit for the mailbox. If the mailbox size reaches or exceeds the specified limit, Exchange prevents the user from sending new messages and displays a descriptive error message
            "prohibitSendReceiveQuota": 102400, // The prohibit send and receive limit for the mailbox. If the mailbox size reaches or exceeds the specified limit, Exchange prevents the mailbox user from sending new messages and won't deliver any new messages to the mailbox. Any messages sent to the mailbox are returned to the sender with a descriptive error message
            "deletedItemCount": 2, // The number of items in the Deleted items folder of the mailbox
            "deletedItemSize": 0,// The size of Deleted items folder of the mailbox
            "firstScanTime": "2025-01-02 04:25:37", // The time when the mailbox was initially scanned into EnPower
            "firstName": null, // The first name of the mailbox user
            "lastName": null, // The last name of the mailbox user
            "alias": "39_Gary_aa_the", //The alias of the mailbox
            "autoReplyEnabled": false, // Indicates whether this mailbox has automatic replies enabled
            "litigationHoldEnabled": true, // Indicates whether this mailbox has litigation hold enabled
            "emailForwardingEnabled": false, //Indicates whether email forwarding is enabled for the mailbox
            "archiveStatus": "Active", // The archiving status of the mailbox
            "archiveName": "", // The name of the folder in the user's mailbox that contains the archive
            "lastActivityDate": "0001-01-01 00:00:00", // The latest date when the mailbox has any activity.
            "forwardingAddressDomain": "", // The domain of the email address that emails are being forwarded to
            "externalForwardingAddressDomain": "",// The domain of the external email address that emails are being forwarded to
            "externalEmailForwardingEnabled": false, // Indicates whether this mailbox is forwarding emails to external email addresses
            "recipientLimits": 500,// The maximum number of allowed recipients on the To, Cc, and Bcc lines of the email message sent from this mailbox
            "mailboxPolicies": { // The mailbox policies applied to this mailbox
                "addressBookPolicy": null, // The address book policy applied to the mailbox
                "retentionPolicy": "Default MRM Policy", // The retention policy applied to the mailbox
                "roleAssignmentPolicy": "Default Role Assignment Policy", // The role assignment policy applied to the mailbox
                "sharingPolicy": "Default Sharing Policy" // The sharing policy applied to the mailbox
            },
            "primaryContact": null, // The Cloud Governance primary contact of the mailbox
            "secondaryContact": null,// The Cloud Governance secondary contact of the mailbox
            "lastRenewalTime": "",// The last time when the mailbox was renewed
            "lastRenewalBy": null,// The latest user who renewed the mailbox
            "renewProfileApplied": null,// Indicates if a renewal profile has been applied to the mailbox
            "metadata": [],// The Cloud Governance metadata associated with the mailbox
            "electionProfileApplied": null,// Indicates if a contact election profile has been applied to the mailbox
            "isRegistered": false,// Indicates if the mailbox has been imported to Cloud Governance
            "phase": "",// The current phase of the mailbox in Cloud Governance.
            "phaseAssignees": "",// The individuals assigned to the current phase of the mailbox in Cloud Governance
            "renewProfile": "N/A", // The Cloud Governance renewal profile applied to the mailbox
            "electionProfile": "N/A",// The Cloud Governance contact election profile applied to the mailbox
            "claimStatus": ""// The Cloud Governance claim status of the mailbox
        }
    ],
    "totalCount": 1,
    "nextLink": ""
}
