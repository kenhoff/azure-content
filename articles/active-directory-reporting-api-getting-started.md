# Getting started with the Azure AD Reporting API

Here's some text telling you why the Reporting API is important and you should totally, totally use it.

(borrowed liberally from https://ahmetalpbalkan.com/blog/azure-rest-api-with-oauth2/)

## Creating an Azure AD application to access the API

(why do we create an application? great question! the answer is Oauth)

### Create the application

### Retrieve the directory ID, client ID, and oauth endpoints

## Retrieving an access token from Azure AD (the oauth flow)

### Get authorization code by punching in a login URL and grabbing the code off of the redirected URL

The URL you should navigate to:

```
https://login.windows.net/<<YOUR-AD-TENANT-ID>>/oauth2/authorize?client_id=<<GUID>>&response_type=code
```

The URL you'll be redirected to, and that you should pull the ```code``` off of:

```
http://localhost/?code=<<SOME LONG STRING HERE>>&session_state=<<GUID>>
```


### Get an access token by making a curl request to the oauth endpoint

```
curl -X POST https://login.windows.net/<<YOUR--AD-TENANT-ID>>/oauth2/token  \
  -F redirect_uri=http://localhost \
  -F grant_type=authorization_code \
  -F resource=https://management.core.windows.net/ \
  -F client_id=87a544fd-... \
  -F code=AwABAAAAvPM1...8sSAA
```

## Making a call to the reporting API, which returns reporting data

This gets all Azure subscription information:

```
curl -v https://management.core.windows.net/subscriptions \
  -H "x-ms-version: 2013-08-01" \
  -H "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciO.....o-ZeMSUbOlC4YEw"
```

And this gets the directory's audit report:

```
curl -v https://service.activedirectory.windowsazure.com:444/api/reports/audit \
  -H "x-ms-version: 2013-08-01" \
  -H "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciO.....o-ZeMSUbOlC4YEw"
```


## When you access token inevitably expires, here's how to tell (programmatically), and how to refresh it

??????
