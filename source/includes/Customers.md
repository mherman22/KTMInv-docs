# Customer

## Customer Overview

Every individual who is referred to as a customer at KTMInv.

All Customers have these characteristics.

## Subresource types

### First Name

* A customer must have a first name which should meet the criteria of a maximum of 20 characters.

### Last Name

* A customer must have a last name which should meet the criteria of a maximum of 20 characters.

### Email Address

* A customer must have an email address which should meet the criteria of a maximum of 20 characters.

### Physical Address

* A customer must have an physical address which should meet the criteria of a maximum of 20 characters.

### Phone Number

* A customer must have a Phone Number which should meet the criteria of a maximum of 20 characters.

## Available Operations for Person type

1. [Get All Customers](#get-all-customers)
2. [Create Customer](#create-a-customer)
3. [Update Customer](#update-a-customer)
4. [Delete Customer](#delete-a-customer)

## get all customers

> get all customers

```shell
GET /ktm/v1/customer/list
```

```java

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
Request request = new Request.Builder()
  .url("/ktm/v1/customer/list")
  .method("GET", null)
  .build();
Response response = client.newCall(request).execute();

```

> Success Response

```response
[
    {
        "customerID": 1,
        "firstName": "rita",
        "lastName": "kaggwa",
        "physicalAddress": "mbra",
        "emailAddress": "ritakagwa@gmail.com",
        "phoneNumber": "0777041946"
    },
    {
        "customerID": 2,
        "firstName": "herman",
        "lastName": "junior",
        "physicalAddress": "kla",
        "emailAddress": "jun@gmail.com",
        "phoneNumber": "0777041946"
    },
    {
        "customerID": 3,
        "firstName": "sheenah",
        "lastName": "arinda",
        "physicalAddress": "kla",
        "emailAddress": "arindaksheenah@gmail.com",
        "phoneNumber": "0777041946"
    },
    {
        "customerID": 4,
        "firstName": "rose",
        "lastName": "nabweteme",
        "physicalAddress": "muyenga",
        "emailAddress": "rose@gmail.com",
        "phoneNumber": "0777042745"
    },
    {
        "customerID": 5,
        "firstName": "mugisha",
        "lastName": "junior",
        "physicalAddress": "kla",
        "emailAddress": "mug@gmail.com",
        "phoneNumber": "0777041946"
    },
    {
        "customerID": 6,
        "firstName": "sarah",
        "lastName": "nabweteme",
        "physicalAddress": "mbra",
        "emailAddress": "nabwetemesara@gmail.com",
        "phoneNumber": "0876887946"
    }
]

```

* Fetch all non-voided Customers that match the search query parameter. Returns a `200 OK` status with the Customer response.

### Parameters

    Parameter | Type | Description
    --- | --- | ---
    *q* | *string* | *search by name* or for listing all the customers `q=all`

## create a customer

> Create a customer

```shell
POST /ktm/v1/customer/create
{      
 "firstName": "john",
    "lastName": "smith",
    "physicalAddress": "usa",
    "emailAddress": "johnsmith@gmail.com",
    "phoneNumber": "0876887946"
}
```

```java

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\r\n    \"names\": [\r\n        {\r\n        \"givenName\": \"Mohit\",\r\n        \"familyName\": \"Kumar\"\r\n        }\r\n    ],\r\n    \"gender\": \"M\",\r\n    \"birthdate\": \"1997-09-02\",\r\n    \"addresses\": [\r\n        {\r\n        \"address1\": \"30, Vivekananda Layout, Munnekolal,Marathahalli\",\r\n        \"cityVillage\": \"Bengaluru\",\r\n        \"country\": \"India\",\r\n        \"postalCode\": \"560037\"\r\n        }\r\n    ]\r\n}\r\n");
Request request = new Request.Builder()
  .url("/ktm/v1/customer/create")
  .method("POST", body)
  .build();
Response response = client.newCall(request).execute();

```

* To create a customer you need to specify the below properties in the request. `401 Unauthorized` is returned if the request is not authenticated or if the authenticated user does not have appropriate permissions.

### Attributes

    Parameter | Type | Description
    --- | --- | ---
    *firstName* | String | The first name of the customer.
    *lastName* | String | The last name of the customer.
    *physicalAddress* | String | The physical address of the customer.
    *emailAddress* | String | The email address of the customer.
    *phoneNumber* | String | The phone number of the customer.

## update a customer

> update a customer

```shell
POST /ktm/v1/customer/4
{
    "emailAddress": "john@smith.com",
}
```

```java

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\r\n    \"gender\": \"M\",\r\n    \"birthdate\": \"1997-01-13\"\r\n}\r\n");
Request request = new Request.Builder()
  .url("/ktm/v1/customer/4")
  .method("POST", body)
  .build();
Response response = client.newCall(request).execute();

```

* Update a customer. This method only modifies properties specified in the request. Returns a `404 Not found`.If not authenticated or authenticated user does not have sufficient privileges, `401 Unauthorized` status is returned.

## delete a customer

> delete a customer

```shell
DELETE /ktm/v1/customer/3
```

```java

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "");
Request request = new Request.Builder()
  .url("/ktm/v1/customer/3")
  .method("DELETE", body)
  .build();
Response response = client.newCall(request).execute();

```

* Delete or Void a target customer. Returns a `404 Not Found` status if person not exists. If not authenticated or authenticated user does not have sufficient privileges, `401 Unauthorized` status is returned.
