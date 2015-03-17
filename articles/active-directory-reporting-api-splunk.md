# Connecting Azure AD security, activity, and audit data to Splunk

Follow this tutorial to get your access token: [Microsoft Azure REST API + OAuth 2.0](https://ahmetalpbalkan.com/blog/azure-rest-api-with-oauth2/)

- Install the [*REST API Modular Input*](https://apps.splunk.com/app/1546/) Splunk app into your Splunk environment.
- Sign into your Splunk environment with an account that has sufficient permissions to add new data sources.
- Click on *Settings* on the top bar, and click *Add Data*.
- Click on *monitor*.
- Click on *REST* on the left bar.
- Fill out the following fields accordingly:
	- REST API Input Name: `Directory Audit data`
	- Endpoint URL: `https://service.activedirectory.windowsazure.com:444/api/reports/audit`
	- HTTP Method: `GET`
	- Authentication Type: `oauth2`
	- OAUTH 2 Token Type: `<none>`
	- OAUTH 2 Access Token: `<access_token from tutorial>`
	- OAUTH 2 Refresh Token: `<refresh_token from tutorial>`
	- OAUTH 2 Token Refresh URL: `https://login.windows.net/c9b13f49-3c25-43c0-a84f-57faf131dc2b/oauth2/token`
	- OAUTH 2 Token Refresh Properties: `grant_type=refresh_token`
	- OAUTH 2 Client ID: `<your client_id from tutorial>`
	- OAUTH 2 Client Secret: `<none>`
	- HTTP Header Properties: `x-ms-version=2013-08-01`
	- URL Arguments: `<none>`
	- Response Type: `xml`
	- Response Handler: `<none>`
	- Response Handler Arguments: `<none>`
	- Response Filter Pattern: `<none>`
	- Streaming Request: `<unchecked>`
	- Index Error Responses: `<unchecked>`
	- HTTP Proxy Address: `<none>`
	- HTTPs Proxy Address: `<none>`
	- Request Timeout: `<none>`
	- Backoff Time: `<none>`
	- Polling Interval: `<none>` 
	- Delimiter: `<none>`
	- Set sourcetype: `Manual`
	- Source type: `xml`

- Click on *Next* at the top.
- Click *Start Searching* to start viewing the data that's been pulled into Splunk. You may need to wait until the first polling interval to see data show up.


Have questions? Get in touch with Ken at [kenhoff@microsoft.com](mailto://kenhoff@microsoft.com?subject=Azure%20AD%20Reporting%20API%20to%20Splunk)

:boom:

