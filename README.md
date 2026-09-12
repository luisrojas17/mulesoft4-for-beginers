# mulesoft4-for-beginers
This repository contains several projects about how to use MuleSoft 4.

## What is MuleSoft
MuleSoft is an integration and automation platform owned by Salesforce, used to connect and integrate applications, legacy systems and modern APIs through API-led connectivity.

On the other hand, API-led connectivity is a methodical approach introduced by MuleSoft to connect data and applications through a tiered network of reusable, purposeful application programming interfaces (APIs)

### The Three Layers of API-led Connectivity

MuleSoft's API-led connectivity approach includes three categories of APIs: [1] (https://www.mulesoft.com/api/types-of-apis),

- System APIs: These sit at the bottom layer to unlock data from core backend systems of record, such as databases, ERPs, and legacy mainframes. They handle basic CRUD (Create, Read, Update, Delete) operations and shield the rest of the architecture from underlying database changes. 
- Process APIs: Sitting in the middle, these APIs take raw data from System APIs and shape, aggregate, or orchestrate it to fulfill specific business logic. They break down data silos without tying business processes to a single data source.
- Experience APIs: Positioned at the top layer, these format data specifically for the end-channel consuming it, such as a mobile app, web browser, or partner system. This is where security policies, user context, and access governance are enforced.

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
Note: In this example you can see how to handle exceptions specially with OnErrorPropagate component.

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

### 30. Connect SAP System using SAP Connector

This example shows how to connect to SAP system. 

For more details go to [Mulesoft documentation page.](https://docs.mulesoft.com/sap-connector/latest/) and [SAP Connector 5.9 Examples](https://docs.mulesoft.com/sap-connector/latest/sap-connector-examples)

For this demo you will require three JAR files:

- IDoc Library: The SAP Java IDoc Library (SAP JIDocLib) is an add-on library for the SAP Java Connector (SAP JCo). It provides an easy-to-use API for sending and receiving IDocs and IDoc packages to and from SAP systems. The API also helps interpreting and navigating through IDocs and modifying them or creating new ones. In addition, it provides a processing feature for parsing and rendering IDoc-XML documents.
- JCo Library: The SAP Java Connector (SAP JCo) is a development library that enables a Java application to communicate with SAP systems via SAP's RFC protocol. he SAP JCo supports both communication directions: inbound Remote Function Calls (Java calls ABAP) as well as outbound Remote Function Calls (ABAP calls Java).
- JCo Native  Library: It depends on the OS.
  - sapjco3.dll for Window
  - slibsapjco3.so for Linux and CloudHub
  - libsapjco3.jnilib or .dylib for macOS

Which you could download from (SAP Marketplace)[https://support.sap.com/en/product/connectors/jco.html?isu_page=1]. However, you must have an active SAP ID (S-User ID) with appropriate software download permissions provided by your company's SAP administrator. These files are proprietary to SAP and cannot be hosted on public Maven central repositories due to licensing.

***Things to know:***

- IDoc (Intermediate Document): A standard data file structure used for asynchronous, batch-based data exchange. 
- BAPI (Business Application Programming Interface): A standard programming function used for real-time, synchronous data exchange.

IDoc and BAPI are two standard methods used to exchange data between SAP systems and external applications.

### 32. Publish Message to IBM MQ using IBM MQ Mule4

This example shows how to connect to IBM MQ system. 

For more details go to [Mulesoft documentation page.](https://docs.mulesoft.com/ibm-mq-connector/latest/)

To test the API developed for this section you will have to use next data:

- URL: http://localhost:38032/sendToIBMMQ
- HTTP Method: GET
- Postman Collection: demo-ibm-mq

The success result is:
```json
{
	"message": "Sending some test message from MuleSoft."
}
```

The failure result is:
```json
{
    "status": "Error",
    "timestamp": "2026-09-10T20:24:10.956693612-06:00",
    "errorType": "IBM-MQ:CONNECTIVITY",
    "message": null,
    "detail": "JMSWMQ0018: No se ha podido conectar con el gestor de colas 'QM1' con modalidad de conexión 'Client' y nombre de host 'localhost(1412)'."
}
```
Note: In this example you can see how to handle exceptions specially with OnErrorContinue component.

### 33. First Successful Router Demo

This example shows how to use First Successful Router. 

For more details go to [Mulesoft documentation page.](https://docs.mulesoft.com/mule-runtime/latest/first-successful)

To test the API developed for this section you will have to use next data:

- URL: http://localhost:38033/first-successful-router-demo
- HTTP Method: GET
- Postman Collection: 33-demo-first-successful-route

The success result is:
```json
{
    "message": "The flow was executed successfully by: 3"
}
```

The failure result is:
```json
{
    "status": "Error",
    "timestamp": "2026-09-10T23:47:32.080709108-06:00",
    "errorType": "MULE:TRANSFORMATION",
    "message": null,
    "detail": "An error occurred."
}
```

### 34. Until Successful Scope Demo

This example shows how to use reties characteristic. 

For more details go to [Mulesoft documentation page.](https://docs.mulesoft.com/mule-runtime/latest/until-successful-scope)

To test the API developed for this section you will have to use next data:

- URL: http://localhost:38034/until-successful-scope-demo
- HTTP Method: GET
- Postman Collection: 34-demo-until-successful-scope

The success result is:
```json
{
    "status": "success",
    "data": [
        {
            "id": 1,
            "employee_name": "Tiger Nixon",
            "employee_salary": 320800,
            "employee_age": 61,
            "profile_image": ""
        },
        {
            "id": 2,
            "employee_name": "Garrett Winters",
            "employee_salary": 170750,
            "employee_age": 63,
            "profile_image": ""
        },
        {
            "id": 3,
            "employee_name": "Ashton Cox",
            "employee_salary": 86000,
            "employee_age": 66,
            "profile_image": ""
        },
        {
            "id": 4,
            "employee_name": "Cedric Kelly",
            "employee_salary": 433060,
            "employee_age": 22,
            "profile_image": ""
        },
        {
            "id": 5,
            "employee_name": "Airi Satou",
            "employee_salary": 162700,
            "employee_age": 33,
            "profile_image": ""
        },
        {
            "id": 6,
            "employee_name": "Brielle Williamson",
            "employee_salary": 372000,
            "employee_age": 61,
            "profile_image": ""
        },
        {
            "id": 7,
            "employee_name": "Herrod Chandler",
            "employee_salary": 137500,
            "employee_age": 59,
            "profile_image": ""
        },
        {
            "id": 8,
            "employee_name": "Rhona Davidson",
            "employee_salary": 327900,
            "employee_age": 55,
            "profile_image": ""
        },
        {
            "id": 24,
            "employee_name": "Doris Wilder",
            "employee_salary": 85600,
            "employee_age": 23,
            "profile_image": ""
        }
    ],
    "message": "Successfully! All records has been fetched."
}
```

The failure result is:
```json
{
    "status": "Error",
    "timestamp": "2026-09-11T17:39:23.921032198-06:00",
    "errorType": "MULE:RETRY_EXHAUSTED",
    "message": "'until-successful' retries exhausted",
    "detail": "HTTP GET on resource 'https://dummy.restapiexample.com:443/api/v1/employees/api/v1/employees' failed: not found (404)."
}
```

Note: This excersice uses next external API https://dummy.restapiexample.com/api/v1/employees.

```json
{
    "status": "success",
    "data": [
        {
            "id": 1,
            "employee_name": "Tiger Nixon",
            "employee_salary": 320800,
            "employee_age": 61,
            "profile_image": ""
        },
        {
            "id": 2,
            "employee_name": "Garrett Winters",
            "employee_salary": 170750,
            "employee_age": 63,
            "profile_image": ""
        },
        {
            "id": 3,
            "employee_name": "Ashton Cox",
            "employee_salary": 86000,
            "employee_age": 66,
            "profile_image": ""
        },
        {
            "id": 4,
            "employee_name": "Cedric Kelly",
            "employee_salary": 433060,
            "employee_age": 22,
            "profile_image": ""
        },
        {
            "id": 5,
            "employee_name": "Airi Satou",
            "employee_salary": 162700,
            "employee_age": 33,
            "profile_image": ""
        },
        {
            "id": 6,
            "employee_name": "Brielle Williamson",
            "employee_salary": 372000,
            "employee_age": 61,
            "profile_image": ""
        },
        {
            "id": 7,
            "employee_name": "Herrod Chandler",
            "employee_salary": 137500,
            "employee_age": 59,
            "profile_image": ""
        },
        {
            "id": 8,
            "employee_name": "Rhona Davidson",
            "employee_salary": 327900,
            "employee_age": 55,
            "profile_image": ""
        },
        {
            "id": 9,
            "employee_name": "Colleen Hurst",
            "employee_salary": 205500,
            "employee_age": 39,
            "profile_image": ""
        },
        {
            "id": 10,
            "employee_name": "Sonya Frost",
            "employee_salary": 103600,
            "employee_age": 23,
            "profile_image": ""
        },
        {
            "id": 11,
            "employee_name": "Jena Gaines",
            "employee_salary": 90560,
            "employee_age": 30,
            "profile_image": ""
        },
        {
            "id": 12,
            "employee_name": "Quinn Flynn",
            "employee_salary": 342000,
            "employee_age": 22,
            "profile_image": ""
        },
        {
            "id": 13,
            "employee_name": "Charde Marshall",
            "employee_salary": 470600,
            "employee_age": 36,
            "profile_image": ""
        },
        {
            "id": 14,
            "employee_name": "Haley Kennedy",
            "employee_salary": 313500,
            "employee_age": 43,
            "profile_image": ""
        },
        {
            "id": 15,
            "employee_name": "Tatyana Fitzpatrick",
            "employee_salary": 385750,
            "employee_age": 19,
            "profile_image": ""
        },
        {
            "id": 16,
            "employee_name": "Michael Silva",
            "employee_salary": 198500,
            "employee_age": 66,
            "profile_image": ""
        },
        {
            "id": 17,
            "employee_name": "Paul Byrd",
            "employee_salary": 725000,
            "employee_age": 64,
            "profile_image": ""
        },
        {
            "id": 18,
            "employee_name": "Gloria Little",
            "employee_salary": 237500,
            "employee_age": 59,
            "profile_image": ""
        },
        {
            "id": 19,
            "employee_name": "Bradley Greer",
            "employee_salary": 132000,
            "employee_age": 41,
            "profile_image": ""
        },
        {
            "id": 20,
            "employee_name": "Dai Rios",
            "employee_salary": 217500,
            "employee_age": 35,
            "profile_image": ""
        },
        {
            "id": 21,
            "employee_name": "Jenette Caldwell",
            "employee_salary": 345000,
            "employee_age": 30,
            "profile_image": ""
        },
        {
            "id": 22,
            "employee_name": "Yuri Berry",
            "employee_salary": 675000,
            "employee_age": 40,
            "profile_image": ""
        },
        {
            "id": 23,
            "employee_name": "Caesar Vance",
            "employee_salary": 106450,
            "employee_age": 21,
            "profile_image": ""
        },
        {
            "id": 24,
            "employee_name": "Doris Wilder",
            "employee_salary": 85600,
            "employee_age": 23,
            "profile_image": ""
        }
    ],
    "message": "Successfully! All records has been fetched."
}
```