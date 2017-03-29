---
title: API Reference

language_tabs:
  - shell
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Function Point API! You can use our Application Program Inteface to access Function Point API endpoints; those can get information on various items from our database.

We currently have language bindings in Shell but soon enough will have other languages as well! To your right hand side you can view code snippets to assist you in using our API, use the upper tabs list to cycle between a couple different languages.

This example API documentation page was created with [Slate](https://github.com/tripit/slate). Feel free to use it as a base for your own API's documentation as well.

# Authentication

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


# Companies

Companies are the central objects in the system. 
Nearly every other object can, on some level, be linked back to a company. 
With access to the API you will be able to:

## Find All Companies
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.

```shell
curl https://api.functionpoint.com/v1.1/companies 
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```


> The above command returns JSON structured like this:

```json
{
	"companies": [
    {
        "ID": "2",
        "name": "Function Point Productivity Software",
        "code": "FP",
        "description": null,
        "addressOne": "200-1622 West 7th Avenue",
        "addressTwo": null,
        "city": "Vancouver",
        "provState": "BC",
        "country": "Canada",
        "postalZip": "V6J 1S5",
        "phone": "604-731-2522",
        "fax": "604-731-3511",
        "webURL": "www.functionpoin.com",
        "statusID": "1",
        "typeID": "3",
        "industryTypeID": "21",
        "classificationID": null,
        "qualificationID": null,
        "accountExecutiveID": null,
        "sourceID": null,
        "companyType": "Office",
        "industryType": null,
        "classification": null,
        "qualification": null,
        "accountExecutive": null,
        "status": "Active",
        "sourceDescription": null
    },
    {
        "ID": "661",
        "name": "Sample Company",
        "code": "SC",
        "description": "Sample company created for the API documentation",
        "addressOne": "123 Main Street",
        "addressTwo": "Unit 456",
        "city": "Townsville",
        "provState": "NY",
        "country": "United States",
        "postalZip": null,
        "phone": null,
        "fax": null,
        "webURL": null,
        "statusID": "1",
        "typeID": "1",
        "industryTypeID": "11",
        "classificationID": "2",
        "qualificationID": "5",
        "accountExecutiveID": "6",
        "sourceID": null,
        "companyType": "Client",
        "industryType": null,
        "classification": "Engaged",
        "qualification": "5 - Client",
        "accountExecutive": null,
        "status": "Active",
        "sourceDescription": null
    }	
	],
	"status": "success",
	"http_code": 200
}
```
This endpoint retrieves all Companies.

### HTTP Request

`GET https://api.functionpoint.com/v1.1/companies`

### Query Parameters

Field | Type | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

## Find a Company by ID
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.

```shell
curl https://api.functionpoint.com/v1.1/companies/661 
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```

> The above command returns JSON structured like this:

```json
{
	"companies": [
		{
			"ID": "661",
			"name": "Sample Company",
			"code": "SC",
			"description": "Sample company created for the API documentation",
			"addressOne": "123 Main Street",
			"addressTwo": "Unit 456",
			"city": "Townsville",
			"provState": "NY",
			"country": "United States",
			"postalZip": null,
			"phone": null,
			"fax": null,
			"webURL": null,
			"statusID": "1",
			"typeID": "1",
			"industryTypeID": "11",
			"classificationID": "2",
			"qualificationID": "5",
			"accountExecutiveID": "6",
			"sourceID": null,
			"companyType": "Client",
			"industryType": null,
			"classification": "Engaged",
			"qualification": "5 - Client",
			"accountExecutive": null,
			"status": "Active",
			"sourceDescription": null
		}
	],
	"status": "success",
	"http_code": 200
}
```

This endpoint retrieves only the Company specified in the URL. The default behaviour is for all fields of a Company to be listed.

### HTTP Request

`GET hhttps://api.functionpoint.com/v1.1/companies/[A_COMPANY_ID]`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

#Contacts

##Find All Contacts
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.
```shell
curl https://api.functionpoint.com/v1.1/contacts
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```

> The above command returns JSON structured like this:

```json
{
  "contacts": [
    {
      "ID": "914",
      "first_name": "Sample",
      "last_name": "Contact",
      "salutation": null,
      "title": null,
      "description": null,
      "home_phone": null,
      "cell_phone": null,
      "direct_phone": null,
      "phone_extension": null,
      "email": null,
      "mailing_list": null,
      "birthdate": null,
      "company_id": "2",
      "company_name": "Function Point Productivity Software",
      "type_id": null,
      "contact_type": null,
      "status_id": "1",
      "contact_status": "Active",
      "staff_status": null,
      "staff_initial": null,
      "role_id": null,
      "is_staff": false
    },
    {
      "ID": "915",
      "first_name": "Sample",
      "last_name": "Contact 2",
      "salutation": null,
      "title": null,
      "description": null,
      "home_phone": null,
      "cell_phone": null,
      "direct_phone": null,
      "phone_extension": null,
      "email": "noone+915@functionpoint.com",
      "mailing_list": null,
      "birthdate": null,
      "company_id": "2",
      "company_name": "Function Point Productivity Software",
      "type_id": null,
      "contact_type": null,
      "status_id": "1",
      "contact_status": "Active",
      "staff_status": null,
      "staff_initial": null,
      "role_id": null,
      "is_staff": false
    },
    ...
    {
      "ID": "916",
      "first_name": "Sample",
      "last_name": "Contact 3",
      "salutation": null,
      "title": null,
      "description": null,
      "home_phone": null,
      "cell_phone": null,
      "direct_phone": null,
      "phone_extension": null,
      "email": null,
      "mailing_list": null,
      "birthdate": null,
      "company_id": "2",
      "company_name": "Function Point Productivity Software",
      "type_id": null,
      "contact_type": null,
      "status_id": "1",
      "contact_status": "Active",
      "staff_status": null,
      "staff_initial": null,
      "role_id": null,
      "is_staff": false
    }
  ],
  "status": "success",
  "http_code": 201
}
```
This endpoint retrieves all contacts.

### HTTP Request

`GET https://api.functionpoint.com/v1.1/contacts`

### Query Parameters

Field | Type | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

##Find a Contact by ID
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.
```shell
curl https://api.functionpoint.com/v1.1/contacts/914
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```

> The above command returns JSON structured like this:

```json
{
  "contacts": 
    {
      "ID": "914",
      "first_name": "Sample",
      "last_name": "Contact",
      "salutation": null,
      "title": null,
      "description": null,
      "home_phone": null,
      "cell_phone": null,
      "direct_phone": null,
      "phone_extension": null,
      "email": null,
      "mailing_list": null,
      "birthdate": null,
      "company_id": "2",
      "company_name": "Function Point Productivity Software",
      "type_id": null,
      "contact_type": null,
      "status_id": "1",
      "contact_status": "Active",
      "staff_status": null,
      "staff_initial": null,
      "role_id": null,
      "is_staff": false
    },
  "status": "success",
  "http_code": 201
}
```
This endpoint retrieves the specified contact.

### HTTP Request

`GET https://api.functionpoint.com/v1.1/contacts/A_CONTACT_ID`

### Query Parameters

Field | Type | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.


#Service Groups

Service Groups are collections of related [Services](#services)

##Find All Service Groups
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.

```shell
curl https://api.functionpoint.com/v1.1/estimate_service_groups
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```

> The above command returns JSON structured like this:

```json
{
    "estimate_service_groups": 
    [
        {
            "ID": "1"
        },
        {
            "ID": "2"
        },
        ...
        {
            "ID": "268"
            
        },
        {
            "ID": "272"
        }
    ],
"count": 100,
"offset": 0,
"more": true,
"status": "success",
"http_code": 200
}

```
This endpoint retrieves all Service Groups.

### HTTP Request

`GET https://api.functionpoint.com/v1.1/estimate_service_groups`

### Query Parameters

Field | Type | Description
--------- | ------- | -----------
estimate_service_group_id | int | Lorem Ipsem
estimate_service_group_name | String | Lorem Ipsem
estimate_service_group_code | String | Lorem Ipsem 
estimate_service_group_order | int | Lorem Ipsem
estimate_service_group_job_id | int | Lorem Ipsem

#Services

##Find All Services
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.

```shell
curl https://api.functionpoint.com/v1.1/estimate_services
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```

> The above command returns JSON structured like this:

```json
{
  "estimate_services": [
		{
			"ID": "1",
			"service_type": "IS",
			"name": "Research",
			"code": "R",
			"order": "2"
		},
		{
			"ID": "2",
			"service_type": "IS",
			"name": "Documentation\/Writing",
			"code": "DW",
			"order": "3"
		},
		{
			"ID": "3",
			"service_type": "IS",
			"name": "Coordination",
			"code": "C",
			"order": "4"
		},
          ...
        {
			"ID": "268",
			"service_type": "IS",
			"name": "Coordination",
			"code": "C",
			"order": "5"
		},
		{
			"ID": "272",
			"service_type": "IS",
			"name": "Copywriting\/Editing",
			"code": "CE",
			"order": "9"
		}
	],
	"count": 100,
	"offset": 0,
	"more": true,
	"status": "success",
	"http_code": 200
}  
```
This endpoint retrieves all _______s.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Field | Type | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.


#Jobs
##Find All Jobs
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.

```shell
curl https://api.functionpoint.com/v1.1/jobs
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```

> The above command returns JSON structured like this:

```json
{
  "jobs": [
    {
      "ID": "5",
      "name": "In-House",
      "number": "30189",
      "status": "Job Overdue",
      "status_alias_of": "Open",
      "is_my_job": "1",
      "project_name": null,
      "company_name": "Function Point Productivity Software",
      "total_seconds_worked": "0"
    },
    {
      "ID": "56",
      "name": "Pro Shop Brochure",
      "number": "30264",
      "status": "Open",
      "status_alias_of": "Open",
      "is_my_job": "1",
      "project_name": null,
      "company_name": "Furry Creek Golf Academy",
      "total_seconds_worked": "0"
    },
    {
      "ID": "58",
      "name": "Pro Shop Signage",
      "number": "30267",
      "status": "Open",
      "status_alias_of": "Open",
      "is_my_job": "1",
      "project_name": null,
      "company_name": "Furry Creek Golf Academy",
      "total_seconds_worked": "0"
    },
    ...
    {
        "ID": "268",
        "service_type": "IS",
        "name": "Coordination",
        "code": "C",
        "order": "5"
    },
    {
        "ID": "272",
        "service_type": "IS",
        "name": "Copywriting\/Editing",
        "code": "CE",
        "order": "9"
    }
],
"count": 100,
"offset": 0,
"more": true,
"status": "success",
"http_code": 200
}
```
This endpoint retrieves all jobs.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Field | Type | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

##Find a Job by ID
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.

```shell
curl https://api.functionpoint.com/v1.1/jobs/5 
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```

> The above command returns JSON structured like this:

```json
{
			"ID": "268",
			"service_type": "IS",
			"name": "Coordination",
			"code": "C",
			"order": "5"
		},
		{
			"ID": "272",
			"service_type": "IS",
			"name": "Copywriting\/Editing",
			"code": "CE",
			"order": "9"
		}
	],
	"count": 100,
	"offset": 0,
	"more": true,
	"status": "success",
	"http_code": 200
}
```
This endpoint retrieves the specified job.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Field | Type | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.



#Offices
##Find an Office by ID
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.

```shell
curl https://api.functionpoint.com/v1.1/offices/2 
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```

> The above command returns JSON structured like this:

```json
{
  "this":"that"
}
```
This endpoint retrieves the specified _______.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Field | Type | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.




#Phases
##Find All phases
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.

```shell
curl https://api.functionpoint.com/v1.1/_______s
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```

> The above command returns JSON structured like this:

```json
{
  "these":[
  {"this":"that"},
  {"this":"that"}
  ]
}
```
This endpoint retrieves all _______s.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Field | Type | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

##Find a phase by ID
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.

```shell
curl https://api.functionpoint.com/v1.1/phase_services/3 
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```

> The above command returns JSON structured like this:

```json
{
  "this":"that"
}
```
This endpoint retrieves the specified phase.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Field | Type | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.



#Tags
##Find All Tags
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.

```shell
curl https://api.functionpoint.com/v1.1/tags
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```

> The above command returns JSON structured like this:

```json
{
  "these":[
  {"this":"that"},
  {"this":"that"}
  ]
}
```
This endpoint retrieves all Tags.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Field | Type | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.


#Tasks
##Find All Tasks
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.

By default, hitting this endpoint without specifying fields will return only the objects' ID numbers.



```shell
curl https://api.functionpoint.com/v1.1/tasks
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```

> The above command returns JSON structured like this:

```json
{
  "tasks": [
      {
        "ID": "217",
        "task_group_id": "1",
        "order": "1",
        "task_group_order_by": null,
        "title": "Research",
        "description": null,
        "service_group_id": null,
        "estimate_service_group_name": null,
        "service_id": null,
        "service_code": null,
        "service_name": null,
        "estimate_service_id": null,
        "estimate_service_code": null,
        "estimate_service_name": null,
        "assigned_by_id": "859",
        "assigned_to_role_id": "8",
        "assigned_by": "ES",
        "created_by_id": null,
        "assigned_by_fullname": "Eddard Stark",
        "assigned_to_role": "AE",
        "assigned_to_role_fullname": "Account Executive",
        "status_id": "1",
        "status": "Draft",
        "percent_complete": "0.00",
        "estimated_hours": "0",
        "actual_hours": "0.00",
        "auth_user_actual_hours": null,
        "start_date_time": "2016-11-30 07:59:00",
        "start_time": "23:59:00",
        "start_date": "2016-11-29",
        "due_date_time": "2016-12-11 07:59:59",
        "due_time": null,
        "due_date": "2016-12-10",
        "priority": null,
        "priority_id": null,
        "milestone_id": null,
        "milestone": null,
        "tags": [
          "Research",
          "Specification and Concept"
        ],
        "timeline_id": "21",
        "estimate_id": "1",
        "is_template": "0",
        "client_printable": "0",
        "docket_id": "1",
        "docket_name": "Corporate Website",
        "docket_number": "30179",
        "docket_status": "8",
        "project_id": "1",
        "project_name": "Corporate Branding Campaign",
        "company_id": "5",
        "company_name": "Great Atlantic Insurance",
        "company_code": "GAD",
        "created_by_fullname": null,
        "docket_status_alias_of": "Open",
        "dependent_tasks": null,
        "type_id": "4",
        "task_contact_id": null,
        "assigned_date": null,
        "creation_date": null,
        "completed_date": null,
        "modified_date": "2016-10-20",
        "task_type": "Time Line Task",
        "base_type": "Task",
        "assignees": [
          {
            "assignee_id": "859",
            "is_primary": "1",
            "full_name": "Eddard Stark",
            "initials": "ES"
          }
        ]
      },
      ...
      {
            "ID": "787",
            "task_group_id": "32",
            "order": "19",
            "task_group_order_by": null,
            "title": "Coding/Testing",
            "description": null,
            "service_group_id": null,
            "estimate_service_group_name": null,
            "service_id": null,
            "service_code": null,
            "service_name": null,
            "estimate_service_id": null,
            "estimate_service_code": null,
            "estimate_service_name": null,
            "assigned_by_id": "1",
            "assigned_to_role_id": null,
            "assigned_by": "ADM",
            "created_by_id": "3",
            "assigned_by_fullname": "Administrator ",
            "assigned_to_role": null,
            "assigned_to_role_fullname": null,
            "status_id": "1",
            "status": "Draft",
            "percent_complete": null,
            "estimated_hours": null,
            "actual_hours": "0.00",
            "auth_user_actual_hours": null,
            "start_date_time": null,
            "start_time": null,
            "start_date": null,
            "due_date_time": null,
            "due_time": null,
            "due_date": null,
            "priority": null,
            "priority_id": null,
            "milestone_id": null,
            "milestone": null,
            "tags": [
              "Coding/Testing",
              "Web Design"
            ],
            "timeline_id": "85",
            "estimate_id": "7",
            "is_template": "0",
            "client_printable": "0",
            "docket_id": "4",
            "docket_name": "Website Re-Design",
            "docket_number": "30185",
            "docket_status": "6",
            "project_id": null,
            "project_name": null,
            "company_id": "6",
            "company_name": "Macdonald and Company",
            "company_code": "MC",
            "created_by_fullname": "Chris Wilson",
            "docket_status_alias_of": "Invoiced",
            "dependent_tasks": null,
            "type_id": "4",
            "task_contact_id": null,
            "assigned_date": null,
            "creation_date": "2011-12-11 05:18:02",
            "completed_date": null,
            "modified_date": "2012-07-13",
            "task_type": "Time Line Task",
            "base_type": "Task",
            "assignees": []
          }
        ],
  "count": 100,
  "offset": 0,
  "more": true,
  "total_count": "1403",
  "status": "success",
  "http_code": 200
}
    
```
This endpoint retrieves all Tasks.

### HTTP Request

`GET https://api.functionpoint.com/v1.1/tasks`
  
### Query Parameters
Parameter | Type | Description
--------- | ------- | -----------
ID  |   lalal  | yaddayaddayadda
task_group_id  |     | 
order  |     | 
task_group_order_by  |     | 
title  |     |  
description  |     |  
service_group_id  |     |  
estimate_service_group_name  |     |  
service_id  |     |  
service_code  |     |  
service_name  |     |  
estimate_service_id  |     |  
estimate_service_code  |     |  
estimate_service_name  |     |  
assigned_by_id  |     | 
assigned_to_role_id  |     | 
assigned_by  |     |  
created_by_id  |     |  
assigned_by_fullname  |     | 
assigned_to_role  |     | 
assigned_to_role_fullname  |     |  
status_id  |     |  
status  |     |  
percent_complete  |     | 
estimated_hours  |     |  
actual_hours  |     |  
auth_user_actual_hours  |     |  
start_date_time  |     |  
start_time  |     |  
start_date  |     |  
due_date_time  |     | 
due_time  |     |  
due_date  |     |  
priority  |     |  
priority_id  |     |  
milestone_id  |     |  
milestone  |     |  
tags  |     | 
timeline_id  |     | 
estimate_id  |     |  
is_template  |     |  
client_printable  |     | 
docket_id  |     | 
docket_name  |     |  
docket_number  |     |  
docket_status  |     | 
project_id  |     |  
project_name  |     |  
company_id  |     |  
company_name  |     |  
company_code  |     |  
created_by_fullname  |     |  
docket_status_alias_of  |     | 
dependent_tasks  |     |  
type_id  |     | 
task_contact_id  |     |  
assigned_date  |     |  
creation_date  |     |  
completed_date  |     |  
modified_date  |     |  
task_type  |     |  
base_type  |     |  
assignees  |     |

##Find a Task by ID
> Make sure to replace `YOUR_ACCESS_TOKEN` with your valid API token.

```shell
curl https://api.functionpoint.com/v1.1/tasks/3671 
  -H "Authorization: OAuth <YOUR_ACCESS_TOKEN>"
```

> The above command returns JSON structured like this:

```json
{
    "tasks": [
      {
        "ID": "217",
        "task_group_id": "1",
        "order": "1",
        "task_group_order_by": null,
        "title": "Research",
        "description": null,
        "service_group_id": null,
        "estimate_service_group_name": null,
        "service_id": null,
        "service_code": null,
        "service_name": null,
        "estimate_service_id": null,
        "estimate_service_code": null,
        "estimate_service_name": null,
        "assigned_by_id": "859",
        "assigned_to_role_id": "8",
        "assigned_by": "ES",
        "created_by_id": null,
        "assigned_by_fullname": "Edard Stark",
        "assigned_to_role": "AE",
        "assigned_to_role_fullname": "Account Executive",
        "status_id": "1",
        "status": "Draft",
        "percent_complete": "0.00",
        "estimated_hours": "0",
        "actual_hours": "0.00",
        "auth_user_actual_hours": null,
        "start_date_time": "2016-11-30 07:59:00",
        "start_time": "23:59:00",
        "start_date": "2016-11-29",
        "due_date_time": "2016-12-11 07:59:59",
        "due_time": null,
        "due_date": "2016-12-10",
        "priority": null,
        "priority_id": null,
        "milestone_id": null,
        "milestone": null,
        "tags": [
          "Research",
          "Specification and Concept"
        ],
        "timeline_id": "21",
        "estimate_id": "1",
        "is_template": "0",
        "client_printable": "0",
        "docket_id": "1",
        "docket_name": "Corporate Website",
        "docket_number": "30179",
        "docket_status": "8",
        "project_id": "1",
        "project_name": "Corporate Branding Campaign",
        "company_id": "5",
        "company_name": "Great Atlantic Insurance",
        "company_code": "GAD",
        "created_by_fullname": null,
        "docket_status_alias_of": "Open",
        "dependent_tasks": null,
        "type_id": "4",
        "task_contact_id": null,
        "assigned_date": null,
        "creation_date": null,
        "completed_date": null,
        "modified_date": "2016-10-20",
        "task_type": "Time Line Task",
        "base_type": "Task",
        "assignees": [
          {
            "assignee_id": "859",
            "is_primary": "1",
            "full_name": "Edard Stark",
            "initials": "ES"
          }
        ]
      },
      ...
      {
        "ID": "787",
        "task_group_id": "32",
        "order": "19",
        "task_group_order_by": null,
        "title": "Coding/Testing",
        "description": null,
        "service_group_id": null,
        "estimate_service_group_name": null,
        "service_id": null,
        "service_code": null,
        "service_name": null,
        "estimate_service_id": null,
        "estimate_service_code": null,
        "estimate_service_name": null,
        "assigned_by_id": "1",
        "assigned_to_role_id": null,
        "assigned_by": "ADM",
        "created_by_id": "3",
        "assigned_by_fullname": "Administrator ",
        "assigned_to_role": null,
        "assigned_to_role_fullname": null,
        "status_id": "1",
        "status": "Draft",
        "percent_complete": null,
        "estimated_hours": null,
        "actual_hours": "0.00",
        "auth_user_actual_hours": null,
        "start_date_time": null,
        "start_time": null,
        "start_date": null,
        "due_date_time": null,
        "due_time": null,
        "due_date": null,
        "priority": null,
        "priority_id": null,
        "milestone_id": null,
        "milestone": null,
        "tags": [
          "Coding/Testing",
          "Web Design"
        ],
        "timeline_id": "85",
        "estimate_id": "7",
        "is_template": "0",
        "client_printable": "0",
        "docket_id": "4",
        "docket_name": "Website Re-Design",
        "docket_number": "30185",
        "docket_status": "6",
        "project_id": null,
        "project_name": null,
        "company_id": "6",
        "company_name": "Macdonald and Company",
        "company_code": "MC",
        "created_by_fullname": "Chris Wilson",
        "docket_status_alias_of": "Invoiced",
        "dependent_tasks": null,
        "type_id": "4",
        "task_contact_id": null,
        "assigned_date": null,
        "creation_date": "2011-12-11 05:18:02",
        "completed_date": null,
        "modified_date": "2012-07-13",
        "task_type": "Time Line Task",
        "base_type": "Task",
        "assignees": []
      }
    ],
    "count": 100,
    "offset": 0,
    "more": true,
    "total_count": "1403",
    "status": "success",
    "http_code": 200
  }
}    
```

This endpoint retrieves the specified Task.

### HTTP Request

`GET https://api.functionpoint.com/v1.1/tasks/`

### Query Parameters
<div class="table">

Parameter | Type | Description
--------- | ------- | -----------
    ID  |     | 
    task_group_id  |     | 
    order  |     | 
    task_group_order_by  |     | 
    title  |     |  
    description  |     |  
    service_group_id  |     |  
    estimate_service_group_name  |     |  
    service_id  |     |  
    service_code  |     |  
    service_name  |     |  
    estimate_service_id  |     |  
    estimate_service_code  |     |  
    estimate_service_name  |     |  
    assigned_by_id  |     | 
    assigned_to_role_id  |     | 
    assigned_by  |     |  
    created_by_id  |     |  
    assigned_by_fullname  |     | 
    assigned_to_role  |     | 
    assigned_to_role_fullname  |     |  
    status_id  |     |  
    status  |     |  
    percent_complete  |     | 
    estimated_hours  |     |  
    actual_hours  |     |  
    auth_user_actual_hours  |     |  
    start_date_time  |     |  
    start_time  |     |  
    start_date  |     |  
    due_date_time  |     | 
    due_time  |     |  
    due_date  |     |  
    priority  |     |  
    priority_id  |     |  
    milestone_id  |     |  
    milestone  |     |  
    tags  |     | 
    timeline_id  |     | 
    estimate_id  |     |  
    is_template  |     |  
    client_printable  |     | 
    docket_id  |     | 
    docket_name  |     |  
    docket_number  |     |  
    docket_status  |     | 
    project_id  |     |  
    project_name  |     |  
    company_id  |     |  
    company_name  |     |  
    company_code  |     |  
    created_by_fullname  |     |  
    docket_status_alias_of  |     | 
    dependent_tasks  |     |  
    type_id  |     | 
    task_contact_id  |     |  
    assigned_date  |     |  
    creation_date  |     |  
    completed_date  |     |  
    modified_date  |     |  
    task_type  |     |  
    base_type  |     |  
    assignees  |     |
  
  </div>