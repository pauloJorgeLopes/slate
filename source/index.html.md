---
title: API Reference

language_tabs:
  - shell
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

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

Welcome to the Function Point API! You can use our Application Program Inteface to access Function Point API endpoints; those can get information on various items from our database.

We currently have language bindings in Shell but soon enough will have other languages as well! To your right hand side you can view code snippets to assist you in using our API, use the upper tabs list to cycle between a couple different languages.

This example API documentation page was created with [Slate](https://github.com/tripit/slate). Feel free to use it as a base for your own API's documentation as well.

# OAuth 

In order to make use of the API 

> Replace YOUR_COMPANY_NAME, YOUR_USER_NAME and YOUR_PASSWORD with the appropriate information

```shell
curl -u cm-user: -X POST https://apidocs.functionpoint.com/v1.1/oauth2/token 
  -d "grant_type=password" 
  -d "username=YOUR_COMPANY_NAME/YOUR_USER_NAME" 
  -d "password=YOUR_PASSWORD" 
  -d "scope=basic"
```
Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: YOUR_ACCESS_TOKEN`