# mulesoft4-for-beginers
This repository contains several projects about how to use MuleSoft 4.

## Local Environment

The local environemnt used by all these project demos was next:

- Anypoint Studio Version 7.24.0
- Mule Server 4.11.0 EE

## Examples

Note: Each example developed used a different HTTP port in case that you require to deploy more than one example at time.


### 22. Salesforce connector (query) Basics and Config from properties

This example shows how to use Salesforce connector to to connect to the Salesforce APIs. The data connection are gotten from config properties file.

For more details go to [Mulesoft documentation page.]
(https://docs.mulesoft.com/salesforce-connector/latest/)

To test the API developed for this section you will have to use next data:

- URL: http://localhost:38022/salesforce-query
- HTTP Method: GET
- Collection: demo-salesforce-query

The success result is:
```json
```

The failure result is:

```json
{
    "status": "Error",
    "timestamp": "2026-09-01T18:56:04.403446268-06:00",
    "errorType": "SALESFORCE:INVALID_INPUT",
    "message": null,
    "detail": "Failed establishing connection with salesforce"
}
```

### 24. Async Scope

To test the API developed for this section you will have to use next data:

- URL: http://localhost:38024/async
- HTTP Method: GET
- Collection: demo-async-scope

This is the message structure gotten from API https://gorest.co.in/public/v2/users used by this excersice.

```json
[
  {
    "id": 8597743,
    "name": "Dharitri Varman",
    "email": "dharitri_varman@casper.test",
    "gender": "female",
    "status": "inactive"
  },
  {
    "id": 8597741,
    "name": "Sudeva Devar DDS",
    "email": "sudeva_devar_dds@mueller.test",
    "gender": "male",
    "status": "active"
  },
  {
    "id": 8597740,
    "name": "Dayaamay Dwivedi DO",
    "email": "do_dayaamay_dwivedi@lehner.test",
    "gender": "male",
    "status": "inactive"
  },
  {
    "id": 8597739,
    "name": "Deeptanshu Talwar",
    "email": "deeptanshu_talwar@keebler-crooks.test",
    "gender": "male",
    "status": "active"
  },
  {
    "id": 8597738,
    "name": "Chandrakin Gandhi",
    "email": "chandrakin_gandhi@jones.test",
    "gender": "male",
    "status": "active"
  },
  {
    "id": 8597737,
    "name": "Bhramar Dubashi",
    "email": "dubashi_bhramar@kiehn.example",
    "gender": "male",
    "status": "active"
  },
  {
    "id": 8597735,
    "name": "Mrs. Gayatri Nayar",
    "email": "mrs_gayatri_nayar@cole-muller.example",
    "gender": "male",
    "status": "inactive"
  },
  {
    "id": 8597734,
    "name": "Mukul Iyengar",
    "email": "iyengar_mukul@white-weimann.test",
    "gender": "male",
    "status": "inactive"
  },
  {
    "id": 8597732,
    "name": "Karthik Pilla Jr.",
    "email": "karthik_pilla_jr@predovic.example",
    "gender": "male",
    "status": "inactive"
  },
  {
    "id": 8597731,
    "name": "Chanakya Nair DO",
    "email": "do_chanakya_nair@haag.example",
    "gender": "male",
    "status": "inactive"
  }
]
```

Note: To see more API examples go to: https://gorest.co.in/

### 25. Round Robin Router

To test the API developed for this section you will have to use next data:

- URL: http://localhost:38025/round-robin-router
- HTTP Method: GET
- Postman Collection: demo-round-robin-route

### 26. Cache Scope

To test the API developed for this section you will have to use next data:

- URL: http://localhost:38026/employee?employeeId=1
- HTTP Method: GET
- Postman Collection: demo-cache-scope

This is the message structure gotten from API: https://reqres.in/api/users used by this excersice.

```json
{
    "data": {
        "id": 1,
        "email": "george.bluth@reqres.in",
        "first_name": "George",
        "last_name": "Bluth",
        "avatar": "https://reqres.in/img/faces/1-image.jpg"
    },
    "support": {
        "url": "https://benhowdle.im/first-cto-playbook?utm_source=reqres&utm_medium=json&utm_campaign=referral",
        "text": "Become a better CTO. A playbook of painful stories and practical advice from a two-time startup CTO."
    },
    "_meta": {
        "powered_by": "ReqRes",
        "docs_url": "https://app.reqres.in/documentation",
        "upgrade_url": "https://app.reqres.in/upgrade",
        "example_url": "https://app.reqres.in/examples/notes-app",
        "variant": "v1_a",
        "message": "Your data persists here. Add auth, logs, and custom schemas to build a real backend.",
        "cta": {
            "label": "See example app",
            "url": "https://app.reqres.in/examples/notes-app"
        },
        "context": "legacy_success"
    }
}
```
### 27. Parse Template

This example shows how to processing a template to obtain a dynamic result. This component could be useful to send emails based on a template where the dynamic private data are.

For more details go to [Mulesoft documentation page.](https://docs.mulesoft.com/mule-runtime/latest/parse-template-reference)

To test the API developed for this section you will have to use next data:

- URL: http://localhost:38027/employee
- HTTP Method: POST
- Postman Collection: demo-parse-template

The success result is a HTML template with data sent it.

### 28. Secure configuration Properties and Secure Configuration Tool

This example shows how to encrypt configuration properties file. The example takes the example developed in the section 22.

For more details go to [Mulesoft documentation page.](https://docs.mulesoft.com/mule-runtime/latest/secure-configuration-properties)

According to the documentation you can use the Secure Properties Tool to encrypt or decrypt text strings. There are two options to use the tool:

- First, you can use online tool hosted on next site: https://secure-properties-api.us-e1.cloudhub.io/
- Second, you can donwload the JAR from next link: https://docs.mulesoft.com/mule-runtime/latest/_attachments/secure-properties-tool-j17.jar

If you prefered donwloading the JAR to use it from your local environment you will have to use next command:

```
java -cp secure-properties-tool-j17.jar com.mulesoft.tools.SecurePropertiesTool \
<method> \
<operation> \
<algorithm> \
<mode> \
<key> \
<value> \
--use-random-iv [optional]
```

For example:

```
java -cp secure-properties-tool-j17.jar com.mulesoft.tools.SecurePropertiesTool \
string \
encrypt \
Blowfish \
CBC \
myKeyTest \
"some value to encrypt"
```

And the output will be: <b>8q5e1+jy0cND2iV2WPThahmz6XsDwB6Z</b>

If you want to decrypt you only have to use "decrypt" word instead of "encrypt". Go to [Parameters Reference](https://docs.mulesoft.com/mule-runtime/latest/secure-configuration-properties#parameter-reference) to see more possible parameters to use with <b>secure-properties-tool-j17.jar</b>

Note: Go to [Supported Algorithms](https://docs.mulesoft.com/mule-runtime/latest/secure-configuration-properties#supported_algorithms) to know all possible options.

### 29. Invoke Java method (static, non-static) from Mule Application

This example shows how to invoke Java methods (either instance or static).

For more details go to [Mulesoft documentation page.](https://docs.mulesoft.com/java-module/latest/java-invoke-method)

To test the API developed for this section you will have to use next data:

- URL: http://localhost:38029/demo-invoke-static-java-method?firstName=Jose%20Luis&secondName=Rojas and http://localhost:38029/demo-invoke-nostatic-java-method?firstName=Jose%20Luis&secondName=Rojas
- HTTP Method: GET
- Postman Collection: demo-invoke-static-java-method and demo-invoke-nostatic-java-method

The success result for both endpoints is:
```json
{
    "message": "Hello Jose Luis Rojas Gomez"
}
```