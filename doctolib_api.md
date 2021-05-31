# Doctolib API

As I couldn't find any (publicly available) API description and/or documentation of Doctolib, I decided to "reverse engineer" the API myself. Hope this helps someone.

JSON Schemas are automatically created via https://www.liquid-technologies.com/online-json-to-schema-converter

### POST /login

#### Description:

Send login information

#### JSON Schema:

```
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "type": "object",
  "properties": { 
    "username": { "type": "string" }, 
    "remember": { "type": "boolean" }, 
    "remember_username": { "type": "boolean" }, 
    "password": { "type": "string" }, 
    "kind": { "type": "string" }
  },
  "required": [ "username", "remember", "remember_username", "password", "kind" ]
}
```

#### Example:
````
{"username":"john.doe@gmail.com","remember":true,"remember_username":true,"password":"s3cret","kind":"patient"}
````

### GET /account/master_patients.json

#### Description

Get info for the logged in user

#### JSON Schema:

```
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "type": "array",
  "items": [ {
      "type": "object",
      "properties": { 
        "id": { "type": "integer" },
        "first_name": { "type": "string" },
        "last_name": { "type": "string" },
        "maiden_name": { "type": "string" },
        "email": { "type": "string" },
        "phone_number": { "type": "string" },
        "zipcode": { "type": "null" },
        "city": { "type": "null" },
        "address": { "type": "null" },
        "gender": { "type": "boolean" },
        "birthdate": { "type": "string" },
        "deleted_at": { "type": "null" },
        "created_at": { "type": "string" },
        "updated_at": { "type": "string" },
        "insurance_sector": { "type": "string" },
        "consented_at": { "type": "null" },
        "city_of_birth_id": { "type": "null" },
        "country_of_birth_id": { "type": "null" },
        "place_of_birth_unknown": { "type": "null" },
        "has_own_email": { "type": "boolean" },
        "has_own_phone_number": { "type": "boolean" },
        "kind": { "type": "string" }
      },
      "required": [ "id", "first_name", "last_name", "maiden_name", "email", "phone_number", "zipcode", "city", "address", "gender", "birthdate", "deleted_at", "created_at", "updated_at", "insurance_sector", "consented_at", "city_of_birth_id", "country_of_birth_id", "place_of_birth_unknown", "has_own_email", "has_own_phone_number", "kind" ]
    }
  ]
}
```

#### Example:
```
[
  {
    "id": 12345678,
    "first_name": "John",
    "last_name": "Doe",
    "maiden_name": "",
    "email": "johndoe@gmail.com",
    "phone_number": "+123456789",
    "zipcode": null,
    "city": null,
    "address": null,
    "gender": false,
    "birthdate": "2099-12-24",
    "deleted_at": null,
    "created_at": "2099-04-05T10:20:09.835+05:00",
    "updated_at": "2099-05-07T12:27:53.435+05:00",
    "insurance_sector": "public",
    "consented_at": null,
    "city_of_birth_id": null,
    "country_of_birth_id": null,
    "place_of_birth_unknown": null,
    "has_own_email": true,
    "has_own_phone_number": true,
    "kind": "main"
  }
]
```
