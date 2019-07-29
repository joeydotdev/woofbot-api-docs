# woofbot.io API Documentation

[woofbot.io](https://woofbot.io) is a free API service that generates dog pictures from an array of different breeds.



# Getting Started
The current version of woofbot.io API lives at `https://api.woofbot.io/v1/`
  - All API calls should be made as `GET` requests and will return a JSON object by default as well as a HTTP status code of 200, if successful.
  - In the event of an API call failing, `status` will have the value of `error` and HTTP status code that is **NOT** 200. Within the response object returned, an element called `message` will be visible stating the error message associated with your call.

# API Bug/Suggestions
We always are welcomed to suggestions to our service. Open up an [issue](https://github.com/joey-colon/woofbot-api-docs/issues) with any feedback you may have for us.

# API Endpoints
### `GET` /breeds
Method is used to obtain the list of breeds that the woofbot.io API currently supports.
`https://api.woofbot.io/v1/breeds`

In the event of a successful reply, the response should look similar to the following:
```json
{
  "status": "success",
  "response": {
    "breeds": [
      "Corgi",
      "Pug",
      "Husky",
      "Golden Retriever",
      "German Shepherd",
      "Pitbull",
      "Shiba",
      "French Bulldog"
    ]
  }
}
```
- `status` - Returns `success` on successful completion of API call
- `response` - Returns API response object
    - `breeds` - An array listing supported breeds
---
### `GET` /breeds/:breed/count
Method is used to obtain the amount of pictures associated with one particular breed.

**Example Call:**
`https://api.woofbot.io/v1/breeds/corgi/count`

In the event of a successful reply, the response should look similar to the following:
```json
{
  "status": "success",
  "response": {
    "count": {
      "amount": 70,
      "breed": "corgi"
    }
  }
}
```
- `status` - Returns `success` on successful completion of API call
- `response` - Returns API response object
    - `count` - Returns `count` object
        - `amount` - Returns amount of pictures woofbot.io has on particular breed
        - `breed` - Returns breed associated with the amount element
---
### `GET` /breeds/:breed/image
Method is used to obtain a random picture associated with one particular breed.

**Example Call:**
`https://api.woofbot.io/v1/breeds/corgi/image`

In the event of a successful reply, the response should look similar to the following:
```json
{
  "status": "success",
  "response": {
    "url": "https://images.woofbot.io/corgi/c8d69b75bd9aff257d9f0c0b95281f56.jpg"
  }
}
```
- `status` - Returns `success` on successful completion of API call
- `response` - Returns API response object
    - `url` - Returns a direct image URL to a picture of the requested breed

