---
title: API Reference

language_tabs:
  - shell : cURL
  - php : PHP

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate/blob/master/README.md'>Documentation Powered by Slate</a>

includes:
  - companies
  - contacts
  - serviceGroups
  - services
  - jobs
  - offices
  - phases
  - tags
  - tasks
  - errors

search: true
---

# Introduction

Welcome to the *Function Point API!* 

You can use our <b>A</b>pplication <b>P</b>rogram <b>I</b>nteface to access Function Point API endpoints. With those we can directly access information from multiple sections from our system.

To make things easier, in the right-hand side you'll find some Copy&Paste-fiendly script samples for you to try out. Right now we are only providing <b>cURL</b> based samples but fear not, fellow dev! Soon enough that upper corner will be filled with tabs for different languages for you to choose from. 

# Authorization 
  
> Replace COMPANY_NAME, USER_NAME and USER_PASSWORD with the appropriate information

```shell
curl --request POST \
  --url https://api.functionpoint.com/v1.1/oauth2/token \
  --header 'content-type: application/x-www-form-urlencoded' \
  --data 'grant_type=password' \
  --data 'username=<COMPANY_NAME>/<USER NAME>' \
  --data 'password=<USER_PASSWORD>' \
  --data 'client_id=cm-user' \
  --data 'scope=basic timesheet'
```

> The above command returns JSON structured like this:

```json
{
  "access_token": "Im1hYyI6IndQeEk2a1J4N091OVZ3ak1PTjZUVmpcL2lXSk0iLCJleHAiOjE0OTEyOTY1OTYsInNjcCI6ImJhc2ljIHRpbWVzaGVldCIsIngiOiJnVXJtIiwidiI6MSwidCI6MiwiY2lkIjoiY20tdXNlciIsImZjbCI6ODAwMjE3NCwiZmNvIjoyOQ",
  "expires_in": 43200,
  "token_type": "bearer",
  "scope": "basic timesheet",
  "refresh_token": "Im1hYyI6Ilo4K1BuaGptbDRaMXZkVVhrV1NBeWRBV0gwbyIsImV4cCI6MCwic2NwIjoiYmFzaWMgdGltZXNoZWV0IiwieCI6IjVRaGgiLCJ2IjoxLCJ0IjozLCJjaWQiOiJjbS11c2VyIiwiZmNsIjo4MDAyMTc0LCJmY28iOjI5"
}
```
> From here on out all FP endpoint hits are required to be accompanied by the provided access_token above 

Well, first things first. Before we can start poking around Function Point we have to set you up with some credentials for the bouncer to let you through. In order to get your credentials, you will need to POST a request to our OAUTH2 endpoint as shown to your right. 

Now, let's dissect this sample POST request to understand it a bit more:

### Scopes
Name | Description
--------- | ------- | -----------
unauthorized_user	| Special scope used internally. It should not come as a shock to you that tokens are NOT granted to those
guest	| Available for any valid user (e.g. a client's client)
basic	| available for any valid staff user
test	| available for any valid user, but only test endpoints should allow this scope
timesheet	| available fro any valid staff user
qb	| only available to users with quickbooks permissions in fpX

