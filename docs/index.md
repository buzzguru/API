# BuzzGuru API

# Introduction
Welcome to the technical overview of the BuzzGuru top API. Below we outline some best practices, error codes and how to access and use the API.

If you have any questions about the process or pricing, you can contact support@buzzguru.com.

# Authentication

## Bearer
You can get your access token inside cabinet https://buzzguru.com/settings/api or contact us by email support@buzzguru.com.

All requests are authenticated based on a bearer token contained in the:

`Authorization` header field where the value is in the format `Bearer {token}`
or `x-access-token` header parameter
or `token` query parameter

# Communications

# Request params

Request params could be in query or inside POST/PUT json body.

## Responses

Correct response has HTTP status code `200`. The data field contain payload with `Number`, `String`, `Object` or `Array` data.

Example of correct response
```json
{
    "ok": true,
    "data": [{
        "some": "items"
    }]
}
```


## Errors
If API returns errors then HTTP status code is different from `200` (corresponding `40x` or `50x` code) and error details are formatted as such;

Example of error response
```json
{
    "ok": false,
    "code": "ERR_CODE",
    "message": "Error text details"
}
```

## Authentication errors

| HTTP status code | Error code | Error description          |
|------------------|------------|----------------------------|
| 401              |   ERR_401  | No access token in request |
| 403              |   ERR_403  | Wrong access token         |


# API Usage

## Top of Instagram channels

`GET /api/v1/top/instagram/channel/`

### Request params

| Name         | Type   | Description      | Default     | Values                                |
|--------------|--------|------------------|-------------|---------------------------------------|
| sortBy       | String | sort type        | subscribers | subscribers, er, likes, views, online |
| limit        | Number | Top output count | 20          | 0-100                                 |
| country      | String | country filter   | null        | [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements) code |


### Response data

| Field         | Types        | Description     |
|---------------|--------------|-------------    |
| _id           | String       |                 |
| avatar        | String, null |                 |
| username      | String, null |                 |
| name          | String, null |                 |
| likes         | Number, null |                 |
| followerCount | Number, null |                 |
| er            | Number, null | 0-100 (Percent) |
| score         | Number, null |                 |
| language      | String, null | [ISO 639-1](https://en.wikipedia.org/wiki/ISO_639-1) code* |
| country       | String, null | [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements) code |


* Except Chinese dialects

### Response example

```json
{
  "code": 0,
  "data": [
    {
      "_id": "25025320",
      "username": "instagram",
      "name": "Instagram",
      "likes": 518324,
      "followerCount": 506820409,
      "er": 0.1,
      "score": 52,
      "language": "en",
      "country": "in",
      "avatar": "https://scontent-dfw5-1.cdninstagram.com/v/t51.2885-19/281440578_1088265838702675_6233856337905829714_n.jpg?stp=dst-jpg_s150x150&_nc_ht=scontent-dfw5-1.cdninstagram.com&_nc_cat=1&_nc_ohc=ZJICX9xf498AX_pEFXx&edm=ABfd0MgBAAAA&ccb=7-5&oh=00_AT_xO55GxgUSKtckwTSIdYZmK5yE1eIwowXgv33YuiRd6A&oe=629347D8&_nc_sid=7bff83",
    }
  ]
}
```