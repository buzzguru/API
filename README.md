# BuzzGuru API

# Introduction
Welcome to the technical overview of the BuzzGuru API. Below we outline some best practices, error codes and how to access and use the API.

If you have any questions about the process or pricing, you can contact support@buzzguru.com.

# Authentication

## bearer
You can get your access token from https://buzzguru.com/settings/api.

All requests are authenticated based on a bearer token contained in the:

`Authorization` header field where the value is in the format `Bearer {token}`
or `access_token` body parameter
or `access_token` query parameter


# Error codes
If API returns errors then HTTP status code is different from `200` (corresponding `40x` or `50x` code) and error details are formatted as such:
```
{
    "error": true,
    "code": Code,
    "message": "…"
}
```

# YouTube

## Search YouTube influencers
`GET /api/youtube/findAll`

### Params

| name                  | type     | Description                       | Example                  |
|-----------------------|----------|-----------------------------------|--------------------------|
| subscribersFrom       | number   | From subscribers                  | 100000                   |
| subscribersTo         | number   | To subscribers                    | 1000000                  |


### Answer
```JSON
[
    {influencerData},
    {influencerData},
    {influencerData}
]
```

------

## Get YouTube influencer data
`GET /api/youtube/findOne`

### Params
| name      | type     | Description                       | Example                  |
|-----------|----------|-----------------------------------|--------------------------|
| _id       | string   | BuzzGuru influencer ID            | 5b61d5e20d7d320017d827fd |
| channelId | string   | YouTube influencer ID             | UC-lHJZR3Gqxm24_Vd_AJ5Yw |
| username  | string   | YouTube influencer username       | PewDiePie                |

### Response
| name                | type     | Description                          | Example                  |
|---------------------|----------|--------------------------------------|--------------------------|
| _id                 | string   | BuzzGuru influencer ID               | 5b61d5e20d7d320017d827fd |
| channelId           | string   | YouTube influencer ID                | UC-lHJZR3Gqxm24_Vd_AJ5Yw |
| username            | string   | YouTube influencer username          | PewDiePie                |
| title               | string   | YouTube influencer title             | PewDiePie                |
| country             | string   | YouTube influencer ISO country code  | us                       |
| banner              | string   | YouTube influencer banner            | URL                      |
| avatar              | string   | YouTube influencer avatar            | URL                      |
| merics.subscribers  | number   | Influencer subscribers               | 111000000                |
| merics.comments     | number   | Influencer median video comments     | 3812                     |
| merics.likes        | number   | Influencer median video likes        | likes                    |
| merics.dislikes     | number   | Influencer  median video dislikes    | 123                      |
| merics.er           | number   | Influencer  median video er          | 6.691612066311273        |
| merics.views        | number   | Influencer  median video views       | 2537477.5                |


### Answer
```JSON
{
    "_id":"5b61d5e20d7d320017d827fd",
    "channelId":"UC-lHJZR3Gqxm24_Vd_AJ5Yw",
    "username":"PewDiePie",
    "title":"PewDiePie",
    "country":"us",
    "banner":"https://yt3.ggpht.com/S44q51b0k25RH1oPdgXOaOSNpbZIL8TCrxCBqUigoMUoai_Cu99psc7zkd-BBgli4pOfzAzk=w2120-fcrop64=1,00000000ffffffff-k-c0xffffffff-no-nd-rj",
    "avatar":"https://yt3.ggpht.com/5oUY3tashyxfqsjO5SGhjT4dus8FkN9CsAHwXWISFrdPYii1FudD4ICtLfuCw6-THJsJbgoY=s900-c-k-c0x00ffffff-no-rj",
    "metrics":{
        "subscribers":111000000,
        "comments":3812,
        "dislikes":0,
        "er":6.691612066311273,
        "likes":167449,
        "views":2537477.5
    }
 }
```




# Twitch

## Search Twitch influencers
`GET /api/twitch/findAll`

### Params

| name                  | type     | Description                       | Example                  |
|-----------------------|----------|-----------------------------------|--------------------------|
| subscribersFrom       | number   | From subscribers                  | 100000                   |
| subscribersTo         | number   | To subscribers                    | 1000000                  |


### Answer
```JSON
[
    {influencerData},
    {influencerData},
    {influencerData}
]
```

------

## Get Twitch influencer data
`GET /api/twitch/findOne`

### Params
| name      | type     | Description                       | Example                  |
|-----------|----------|-----------------------------------|--------------------------|
| _id       | string   | BuzzGuru influencer ID            | 5b61d5e20d7d320017d827fd |
| channelId | string   | Twitch influencer ID              | UC-lHJZR3Gqxm24_Vd_AJ5Yw |
| username  | string   | Twitch influencer username        | PewDiePie                |

### Response
| name                | type     | Description                          | Example                  |
|---------------------|----------|--------------------------------------|--------------------------|
| _id                 | string   | BuzzGuru influencer ID               | 5b61d5e20d7d320017d827fd |
| channelId           | string   | YouTube influencer ID                | UC-lHJZR3Gqxm24_Vd_AJ5Yw |
| username            | string   | YouTube influencer username          | PewDiePie                |
| title               | string   | YouTube influencer title             | PewDiePie                |
| country             | string   | YouTube influencer ISO country code  | us                       |
| banner              | string   | YouTube influencer banner            | URL                      |
| avatar              | string   | YouTube influencer avatar            | URL                      |
| merics.subscribers  | number   | Influencer subscribers               | 111000000                |
| merics.comments     | number   | Influencer median video comments     | 3812                     |
| merics.likes        | number   | Influencer median video likes        | likes                    |
| merics.dislikes     | number   | Influencer  median video dislikes    | 123                      |
| merics.er           | number   | Influencer  median video er          | 6.691612066311273        |
| merics.views        | number   | Influencer  median video views       | 2537477.5                |


### Answer
```JSON
{
    "_id":"5b61d5e20d7d320017d827fd",
    "channelId":"UC-lHJZR3Gqxm24_Vd_AJ5Yw",
    "username":"PewDiePie",
    "title":"PewDiePie",
    "country":"us",
    "banner":"https://yt3.ggpht.com/S44q51b0k25RH1oPdgXOaOSNpbZIL8TCrxCBqUigoMUoai_Cu99psc7zkd-BBgli4pOfzAzk=w2120-fcrop64=1,00000000ffffffff-k-c0xffffffff-no-nd-rj",
    "avatar":"https://yt3.ggpht.com/5oUY3tashyxfqsjO5SGhjT4dus8FkN9CsAHwXWISFrdPYii1FudD4ICtLfuCw6-THJsJbgoY=s900-c-k-c0x00ffffff-no-rj",
    "metrics":{
        "subscribers":111000000,
        "comments":3812,
        "dislikes":0,
        "er":6.691612066311273,
        "likes":167449,
        "views":2537477.5
    }
 }
```



# TikTok

## Search TikTok influencers
`GET /api/tiktok/findAll`

### Params

| name                  | type     | Description                       | Example                  |
|-----------------------|----------|-----------------------------------|--------------------------|
| subscribersFrom       | number   | From subscribers                  | 100000                   |
| subscribersTo         | number   | To subscribers                    | 1000000                  |


### Answer
```JSON
[
    {influencerData},
    {influencerData},
    {influencerData}
]
```

------

## Get TikTok influencer data
`GET /api/tiktok/findOne`

### Params
| name      | type     | Description                       | Example                  |
|-----------|----------|-----------------------------------|--------------------------|
| _id       | string   | BuzzGuru influencer ID            | 5b61d5e20d7d320017d827fd |
| channelId | string   | TikTok influencer ID              | UC-lHJZR3Gqxm24_Vd_AJ5Yw |
| username  | string   | TikTok influencer username        | PewDiePie                |

### Response
| name                | type     | Description                          | Example                  |
|---------------------|----------|--------------------------------------|--------------------------|
| _id                 | string   | BuzzGuru influencer ID               | 5b61d5e20d7d320017d827fd |
| channelId           | string   | YouTube influencer ID                | UC-lHJZR3Gqxm24_Vd_AJ5Yw |
| username            | string   | YouTube influencer username          | PewDiePie                |
| title               | string   | YouTube influencer title             | PewDiePie                |
| country             | string   | YouTube influencer ISO country code  | us                       |
| banner              | string   | YouTube influencer banner            | URL                      |
| avatar              | string   | YouTube influencer avatar            | URL                      |
| merics.subscribers  | number   | Influencer subscribers               | 111000000                |
| merics.comments     | number   | Influencer median video comments     | 3812                     |
| merics.likes        | number   | Influencer median video likes        | likes                    |
| merics.dislikes     | number   | Influencer  median video dislikes    | 123                      |
| merics.er           | number   | Influencer  median video er          | 6.691612066311273        |
| merics.views        | number   | Influencer  median video views       | 2537477.5                |


### Answer
```JSON
{
    "_id":"5b61d5e20d7d320017d827fd",
    "channelId":"UC-lHJZR3Gqxm24_Vd_AJ5Yw",
    "username":"PewDiePie",
    "title":"PewDiePie",
    "country":"us",
    "banner":"https://yt3.ggpht.com/S44q51b0k25RH1oPdgXOaOSNpbZIL8TCrxCBqUigoMUoai_Cu99psc7zkd-BBgli4pOfzAzk=w2120-fcrop64=1,00000000ffffffff-k-c0xffffffff-no-nd-rj",
    "avatar":"https://yt3.ggpht.com/5oUY3tashyxfqsjO5SGhjT4dus8FkN9CsAHwXWISFrdPYii1FudD4ICtLfuCw6-THJsJbgoY=s900-c-k-c0x00ffffff-no-rj",
    "metrics":{
        "subscribers":111000000,
        "comments":3812,
        "dislikes":0,
        "er":6.691612066311273,
        "likes":167449,
        "views":2537477.5
    }
 }
```




# Instagram

## Search Instagram influencers
`GET /api/instagram/findAll`

### Params

| name                  | type     | Description                       | Example                  |
|-----------------------|----------|-----------------------------------|--------------------------|
| subscribersFrom       | number   | From subscribers                  | 100000                   |
| subscribersTo         | number   | To subscribers                    | 1000000                  |


### Answer
```JSON
[
    {influencerData},
    {influencerData},
    {influencerData}
]
```

------

## Get Instagram influencer data
`GET /api/instagram/findOne`

### Params
| name      | type     | Description                       | Example                  |
|-----------|----------|-----------------------------------|--------------------------|
| _id       | string   | BuzzGuru influencer ID            | 5b61d5e20d7d320017d827fd |
| channelId | string   | Instagram influencer ID              | UC-lHJZR3Gqxm24_Vd_AJ5Yw |
| username  | string   | Instagram influencer username        | PewDiePie                |

### Response
| name                | type     | Description                          | Example                  |
|---------------------|----------|--------------------------------------|--------------------------|
| _id                 | string   | BuzzGuru influencer ID               | 5b61d5e20d7d320017d827fd |
| channelId           | string   | YouTube influencer ID                | UC-lHJZR3Gqxm24_Vd_AJ5Yw |
| username            | string   | YouTube influencer username          | PewDiePie                |
| title               | string   | YouTube influencer title             | PewDiePie                |
| country             | string   | YouTube influencer ISO country code  | us                       |
| banner              | string   | YouTube influencer banner            | URL                      |
| avatar              | string   | YouTube influencer avatar            | URL                      |
| merics.subscribers  | number   | Influencer subscribers               | 111000000                |
| merics.comments     | number   | Influencer median video comments     | 3812                     |
| merics.likes        | number   | Influencer median video likes        | likes                    |
| merics.dislikes     | number   | Influencer  median video dislikes    | 123                      |
| merics.er           | number   | Influencer  median video er          | 6.691612066311273        |
| merics.views        | number   | Influencer  median video views       | 2537477.5                |


### Answer
```JSON
{
    "_id":"5b61d5e20d7d320017d827fd",
    "channelId":"UC-lHJZR3Gqxm24_Vd_AJ5Yw",
    "username":"PewDiePie",
    "title":"PewDiePie",
    "country":"us",
    "banner":"https://yt3.ggpht.com/S44q51b0k25RH1oPdgXOaOSNpbZIL8TCrxCBqUigoMUoai_Cu99psc7zkd-BBgli4pOfzAzk=w2120-fcrop64=1,00000000ffffffff-k-c0xffffffff-no-nd-rj",
    "avatar":"https://yt3.ggpht.com/5oUY3tashyxfqsjO5SGhjT4dus8FkN9CsAHwXWISFrdPYii1FudD4ICtLfuCw6-THJsJbgoY=s900-c-k-c0x00ffffff-no-rj",
    "metrics":{
        "subscribers":111000000,
        "comments":3812,
        "dislikes":0,
        "er":6.691612066311273,
        "likes":167449,
        "views":2537477.5
    }
 }
```













