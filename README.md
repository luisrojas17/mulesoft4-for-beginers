# mulesoft4-for-beginers
This repository contains several projects about how to use MuleSoft 4.

## Examples

Note: Each example developed used a different HTTP port in case that you require to deploy more than one example at time.

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

To test the API developed for this section you will have to use next data:

- URL: http://localhost:38027/employee
- HTTP Method: POST
- Postman Collection: demo-parse-template

The output is an HTML template with data sent it.