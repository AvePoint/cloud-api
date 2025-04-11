# Explore EnPower Public API

With EnPower Public API, you can access and retrieve your cloud objects details, including both their properties in Microsoft admin centers and in EnPower to form your own reports or audit your data by integrating with other platforms or services. 

The following sections provide detailed descriptions of each data retrieval method, including the required permissions, query parameters, and the structure of the responses. These methods are essential tools for administrators and developers who need to analyze their cloud objects managed by EnPower.


## API Methods for Power Platform Data Retrieval

Currently, Power Platform objects can be retrieved via the following API Methods.

| API Method | Endpoint | Documentation | 
|--- | --- | --- |
| GET | `/smp/powerplatform/environments` | [Environments](../enpower/powerplatform/environments.md) |
| GET | `/smp/powerplatform/connections` | [Connections](../enpower/powerplatform/connections.md) |
| GET | `/smp/powerplatform/powerapps` | [Power Apps](../enpower/powerplatform/powerapps.md) |
| GET | `/smp/powerplatform/powerautomate/cloudflows` | [Power Automate Cloud Flows](../enpower/powerplatform/cloudflows.md) |
| GET  | `/smp/powerplatform/powerbi/workspaces` | [Power BI Workspaces](../enpower/powerplatform/workspaces.md) |
| GET | `/smp/powerplatform/powerbi/artifacts` | [Power BI Artifacts](../enpower/powerplatform/artifacts.md) |


## API Methods for Exchange Data Retrieval

With the following API Methods, data of your resource mailboxes, shared mailboxes, and user mailboxes can be retrieved.

| API Method | Endpoint | Documentation | 
|--- | --- | --- |
| GET | `/smp/exchange/resourcemailboxes` | [Resource Mailboxes](../enpower/exchange/resourcemailboxes.md) |
| GET | `/smp/exchange/mailboxes` | [User or Shared Mailboxes](../enpower/exchange/userandsharedmailboxes.md) |
