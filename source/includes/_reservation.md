# Reservations

## The reservation object

> The reservation object

```json
{
  "id": "424hgd03483sdf08",
  "type": "meet",
  "description": "Jane Doe's meeting with clients",
  "member_id": "sdfnsghs98358sdf",
  "company_id": "8sd9sdghsgj838fp",
  "resource_id": "59349sdfjsd8394s",
  "location_id": "dsjgnxcmdsfhsjdf",
  "total_amount": {
    "amount": 100.00,
    "fees": 5.00,
    "tax": 10.00,
    "currency": "USD"
  },
  "is_canceled": false,
  "start_time": "2021-05-22T09:00:00.000Z",
  "end_time": "2021-05-22T10:00:00.000Z"
}
```

Attribute | Type | Description
--------- | ------- | -----------
id | string | Unique identifier for the object
type | string | Type of reservation. One of 'meet', 'share' or 'team'
description | string | Description of the reservation
member_id | string | Unique identifier of the member who is reserving the resource
company_id | string | Unique identifier of the company who is reserving the resource
resource_id | string | Unique identifier of the resource being reserved
location_id | string | Unique identifier of the location where the resource is being reserved
total_amount | total_amount object | Total amount to be paid for the reservation
is_canceled | boolean | Whether the reservation has been canceled or not. Defaults to false
start_time | string | Start time of the reservation
end_time | string | End time of the reservation

### The total_amount object


Attribute | Type | Description
--------- | ------- | -----------
amount | float value | Base price of the resource being reserved.
fees | float_value | Applicable fees, if any, for the resource being reserved.
tax | float_value | Applicable tax, if any
currency | string | Three letter ISO currency code.

## Create a reservation

```shell
curl "https://sandbox-aloha-api.cbre.com/v1/reservations" \
  -H "Authorization: aloha_secret_key" \
  -H "Content-Type: application/json" \
  -d type="meet" \
  -d description="Jane's internal team meeting" \
  -d member_id="sdfnsghs98358sdf" \
  -d resource_id="59349sdfjsd8394s" \
  -d start_time="2021-05-22T09:00:00.000Z" \
  -d end_time="2021-05-22T09:00:00.000Z"
```

```go
TBD
```

```java
TBD
```

```python
TBD
```

> Response

```json
{
  "id": "424hgd03483sdf08",
  "type": "meet",
  "description": "Jane Doe's meeting with clients",
  "member_id": "sdfnsghs98358sdf",
  "company_id": "8sd9sdghsgj838fp",
  "resource_id": "59349sdfjsd8394s",
  "location_id": "dsjgnxcmdsfhsjdf",
  "total_amount": {
    "amount": 100.00,
    "fees": 5.00,
    "tax": 10.00,
    "currency": "USD"
  },
  "is_canceled": false,
  "start_time": "2021-05-22T09:00:00.000Z",
  "end_time": "2021-05-22T10:00:00.000Z"
}
```

### HTTP Request

`POST https://sandbox-aloha-api.cbre.com/v1/reservations`

### URL Parameters

`NONE`

### Query Parameters

`NONE`

### Request Body

Attribute | Type | Required? | Description
--------- | ------- | ---------- | -----------
type | string | required | Type of reservation. One of 'meet', 'share' or 'team'
description | string | optional | Description of the reservation
member_id | string | required | Unique identifier of the member who is reserving the resource
resource_id | string | required | Unique identifier of the resource being reserved
start_time | string | required | Start time of the reservation
end_time | string | required | End time of the reservation

## Update a reservation

```shell
curl "https://sandbox-aloha-api.cbre.com/v1/reservations" \
  -H "Authorization: aloha_secret_key" \
  -H "Content-Type: application/json" \
  -d type="meet" \
  -d description="Jane's internal team meeting" \
  -d member_id="sdfnsghs98358sdf" \
  -d resource_id="59349sdfjsd8394s" \
  -d is_canceled=true \
  -d start_time="2021-05-22T09:00:00.000Z" \
  -d end_time="2021-05-22T09:00:00.000Z"
```

```go
TBD
```

```java
TBD
```

```python
TBD
```

> Response

```json
{
  "id": "424hgd03483sdf08",
  "type": "meet",
  "description": "Jane Doe's meeting with clients",
  "member_id": "sdfnsghs98358sdf",
  "company_id": "8sd9sdghsgj838fp",
  "resource_id": "59349sdfjsd8394s",
  "location_id": "dsjgnxcmdsfhsjdf",
  "total_amount": {
    "amount": 100.00,
    "fees": 5.00,
    "tax": 10.00,
    "currency": "USD"
  },
  "is_canceled": true,
  "start_time": "2021-05-22T09:00:00.000Z",
  "end_time": "2021-05-22T10:00:00.000Z"
}
```

### HTTP Request

`PUT https://sandbox-aloha-api.cbre.com/v1/reservations/:id`

<aside class="notice">
    Use the update reservation endpoint to cancel a reservation.
</aside>

### URL Parameters

Parameter | Description
--------- | -----------
id | Unique identifier of the reservation object

### Query Parameters

`NONE`

### Request Body

Attribute | Type | Required? | Description
--------- | ------- | ---------- | -----------
type | string | optional | Type of reservation. One of 'meet', 'share' or 'team'
description | string | optional | Description of the reservation
member_id | string | optional | Unique identifier of the member who is reserving the resource
resource_id | string | optional | Unique identifier of the resource being reserved
is_canceled | boolean | optional | Whether the reservation has been canceled or not. Defaults to false
start_time | string | optional | Start time of the reservation
end_time | string | optional | End time of the reservation

## Get all reservations

```shell
curl "https://sandbox-aloha-api.cbre.com/v1/reservations" \
  -H "Authorization: aloha_secret_key" \
  -H "Content-Type: application/json"
```

```go
TBD
```

```java
TBD
```

```python
TBD
```

> Response

```json
[
  {
    "id": "424hgd03483sdf08",
    "type": "meet",
    "description": "Jane Doe's meeting with clients",
    "member_id": "sdfnsghs98358sdf",
    "company_id": "8sd9sdghsgj838fp",
    "resource_id": "59349sdfjsd8394s",
    "location_id": "dsjgnxcmdsfhsjdf",
    "total_amount": {
      "amount": 100.00,
      "fees": 5.00,
      "tax": 10.00,
      "currency": "USD"
    },
    "is_canceled": false,
    "start_time": "2021-05-22T09:00:00.000Z",
    "end_time": "2021-05-22T10:00:00.000Z"
  },
  {
    "id": "98sdfgjsd78sdf9s",
    "type": "team",
    "description": "Jane Doe's meeting with clients",
    "member_id": "ls7g8sdg0sngsjsd",
    "company_id": "1039sgjsgjsdgks8",
    "resource_id": "202sdgjgsdfgjs88",
    "location_id": "jsdls87348sdfjs0",
    "total_amount": {
      "amount": 200.00,
      "fees": 15.00,
      "tax": 20.00,
      "currency": "USD"
    },
    "is_canceled": false,
    "start_time": "2021-06-23T09:00:00.000Z",
    "end_time": "2021-06-23T10:00:00.000Z"
  }
]
```

### HTTP Request

`GET https://sandbox-aloha-api.cbre.com/v1/reservations`

### URL Parameters

`NONE`

### Query Parameters

Parameter | Type | Required | Description
--------- | ------- | ---------- | -----------
type | string | optional | Returns all reservations of this type
member_id | string | optional | Returns all reservations reserved by that particular member
company_id | string | optional | Returns all reservations reserved for that particular company
resource_id | string | optional | Returns all reservations for only that particular resource
location_id | string | optional | Returns all reservations for only that particular location
is_canceled | boolean | optional | Returns all canceled/not canceled reservations

### Request Body

`NONE`

## Get a single reservation

```shell
curl "https://sandbox-aloha-api.cbre.com/v1/reservations/:id" \
  -H "Authorization: aloha_secret_key" \
  -H "Content-Type: application/json"
```

```go
TBD
```

```java
TBD
```

```python
TBD
```

> Response

```json
{
  "id": "424hgd03483sdf08",
  "type": "meet",
  "description": "Jane Doe's meeting with clients",
  "member_id": "sdfnsghs98358sdf",
  "company_id": "8sd9sdghsgj838fp",
  "resource_id": "59349sdfjsd8394s",
  "location_id": "dsjgnxcmdsfhsjdf",
  "total_amount": {
    "amount": 100.00,
    "fees": 5.00,
    "tax": 10.00,
    "currency": "USD"
  },
  "is_canceled": false,
  "start_time": "2021-05-22T09:00:00.000Z",
  "end_time": "2021-05-22T10:00:00.000Z"
}
```

### HTTP Request

`GET https://sandbox-aloha-api.cbre.com/v1/reservations/:id`

### URL Parameters

Parameter | Description
--------- | -----------
id | Unique identifier of the reservation object

### Query Parameters

`NONE`

### Request Body

`NONE`
