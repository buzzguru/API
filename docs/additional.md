

## Top of Youtube channels

`GET /api/v1/top/youtube/channel/`

### Request params
| Name         | Type   | Description      | Values                                | Default     |
|--------------|--------|------------------|---------------------------------------|-------------|
| sortBy       | String | sort type        | subscribers, er, likes, views, online | subscribers |
| limit        | Number | Top output count | 0-100                                 | 20          |


------

### Youtube response
```json
{
  "code": 0,
  "data": [
      {
        "_id": "5bb03293e8b47300178867a0",
        "views": 148640.5,
        "language": "en",
        "subscribers": 216000000,
        "title": "T-Series",
        "country": "in",
        "username": "tseries",
        "avatar": "https://yt3.ggpht.com/hTPDN-Yr7vQCEJ-YxDyH6OiSAMUcPd0gW40Dxy4299GFFBPh3lumCXIZhMQnOVGV6n3a1GL4BQ=s900-c-k-c0x00ffffff-no-rj",
        "er": 2.6947266730605524,
      }
    ]
}
```
### Possible Youtube response types
```
| Field       | Types        |
|-------------|--------------|
| _id         | String       |
| views       | Number, null |
| language    | String, null |
| subscribers | Number, null |
| title       | String, null |
| country     | String, null |
| username    | String, null |
| avatar      | String, null |
| er          | Number, null |
```
------
### Tiktok response
```json
{
    "code": 0,
    "data": [
        {
            "_id": "5831967",
            "country": "us",
            "language": "en",
            "name": "charli d’amelio",
            "avatar": "https://p16-va.tiktokcdn.com/tos-maliva-avt-0068/5919c31d26416a1a795bb264549a3e14~c5_720x720.jpeg",
            "followerCount": 141037520,
            "avgLikeCount": 1425304.41,
            "avgViewCount": 10900577.94,
            "er": 21.97,
        }
    ]
}
```
### Possible Tiktok response types
```
| Field         | Types        |
|---------------|--------------|
| _id           | String       |
| country       | String, null |
| language      | String, null |
| name          | String, null |
| avatar        | String, null |
| followerCount | Number, null |
| avgLikeCount  | Number, null |
| avgViewCount  | Number, null |
| er            | Number, null |
```
------
### Twitch response
```
{
    "code": 0,
    "data": [
        {
            "_id": "5f6273b9ffbe66c6904ed76a",
            "avgViewsCount": 0,
            "avgViewersCount": 12586,
            "er": 0.68,
            "language": "en",
            "avatar": "https://static-cdn.jtvnw.net/jtv_user_pictures/fef9fc35-20a0-4884-8ee1-10ab74c22687-profile_image-300x300.png",
            "subscribers": 18218233,
            "title": "Ninja",
            "username": "ninja"
        }
    ]
}
```
### Possible Twitch response types
```
| Field           | Types        |
|-----------------|--------------|
| _id             | String       |
| avgViewsCount   | Number, null |
| avgViewersCount | Number, null |
| er              | Number, null |
| language        | String, null |
| avatar          | String, null |
| subscribers     | Number, null |
| title           | String, null |
| username        | String, null |
```
