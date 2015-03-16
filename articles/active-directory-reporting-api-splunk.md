# Connecting Azure AD security, activity, and audit data to Splunk

Follow this tutorial to get your access token: [Microsoft Azure REST API + OAuth 2.0](https://ahmetalpbalkan.com/blog/azure-rest-api-with-oauth2/)

- Get the Modular REST input for Splunk from the splunk app store
- From your Splunk instance, click Add Data -> Monitor -> REST
	- REST API Input Name: Your Directory's Security, Activity, and Audit data
	- Endpoint URL: https://reportingservice.activedirectory.windowsazure.com/kenhoffdemo.onmicrosoft.com/reports
	- HTTP Method: GET
	- Authentication Type: oauth2
	- OAUTH 2 Token Type: <none>
	- OAUTH 2 Access Token: <access_token from tutorial>
	- OAUTH 2 Refresh Token: <refresh_token from tutorial>
	- OAUTH 2 Token Refresh URL: https://login.windows.net/c9b13f49-3c25-43c0-a84f-57faf131dc2b/oauth2/token
	- OAUTH 2 Token Refresh Properties: grant_type=refresh_token
	- OAUTH 2 Client ID: <your client_id from tutorial>
	- OAUTH 2 Client Secret: <none>
	- HTTP Header Properties: x-ms-version=2013-08-01
	- URL Arguments: 
	- Response Type:
	- Response Handler:
	- Response Handler Arguments:
	- Response Filter Pattern:
	- Streaming Request:
	- Index Error Responses:
	- HTTP Proxy Address:
	- HTTPs Proxy Address:
	- Request Timeout:
	- Backoff Time:
	- Polling Interval: 
	- Delimiter: `<none>`
	- Set sourcetype: Manual
	- Source type: xml


