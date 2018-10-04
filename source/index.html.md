---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - php
  - ruby
  - python
  - javascript
  

toc_footers:
  - <a href='mailto:contact@fake.com'>Contact Us</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Bowling API! You can use our API to access Bowling API endpoints, which can get information on players, games and scores in our database.


# Authentication

> To authorize, use this code:

```ruby
require 'open-uri'

url = "https://samplebowlingapi.com/api/v1/<ENDPOINT>"

data = open(url).read
```

```python

#python code pending


```

```php

$ch = curl_init("https://samplebowlingapi.com/api/v1/<ENDPOINT>");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HEADER, 0);
$data = curl_exec($ch);
curl_close($ch);

```

```javascript
//javascript code pending
```

> Make sure to replace `<ENDPOINT>` with the desired resource/endpoint.

Bowling does not yet use API keys to allow access to the API. It is currently open access.

<!--
<aside class="notice">
Contact: team@samplebowlingapi.com with any questions regarding access.
</aside>
-->

Bowling expects a resource/endpoint to be included in all API requests to the server.

-->

For example, a valid request to the players endpoint would look like:

`https://samplebowlingapi.com/api/v1/players`

<!--
<aside class="notice">
You must replace <code>your_api_key</code> with your personal API key.
</aside>
-->

# Players

## Create a Player

```ruby
require 'rest-client'

url = "https://samplebowlingapi.com/api/v1/players"

response = RestClient.post url, {first_name: 'John', last_name: "Smith"}

data = response.body
```

```python
#python code pending
```

```php

$ch = curl_init("https://samplebowlingapi.com/api/v1/players");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HEADER, 0);
$data = curl_exec($ch);
curl_close($ch);

```

```javascript
//javascript code pending
```

> The above command returns JSON structured like this:

```json
  { 
    "data": {
      "entity_type": "Player",
      "entity_id": 1,
      "last_updated_at_unix": 1516747617,
      "generated_at_unix": 1516751509,
      "first_name": "John",
      "last_name": "Smith",
      "gender": "Male",
      "bio": "John is a professional bowler with a handicap of XYZ",
      "average_score": 201.2,
      "games": [
        {
          "individual_score": 130.0,
          "record_url": "https://samplebowlingapi.com/api/v1/games/1"
        },
        {
          "individual_score": 130.0,
          "record_url": "https://samplebowlingapi.com/api/v1/games/2"
        },
      ]
    },
  }
```

This endpoint creates a player.


### HTTP Request

`POST https://samplebowlingapi.com/api/v1/players`

### URL Parameters


Parameter | Type | Description
--------- | ------- | -----------
first_name | String | The first name of player
last_name | String | The last name of player
gender | String | The gender of player (male, female or other)
bio | String | The biography of player


### Fields Returned

Field | Type | Description
--------- | ------- | -----------
data | Object | Container object for all entity data
entity_type | String | Entity/Record type
entity_id | Integer | Unique ID for given entity type
first_name | String | First name of player
last_name | String | Last name of player
gender | String | Gender of player
bio | String | Biography of player
average_score | Decimal | Average score across all games for player
games | Array | Array of all game data for player

## Get a Specific Player

```ruby
require 'open-uri'

url = "https://samplebowlingapi.com/api/v1/players/1"

data = open(url).read
```

```python
#python code pending
```

```php

$ch = curl_init("https://samplebowlingapi.com/api/v1/players/1");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HEADER, 0);
$data = curl_exec($ch);
curl_close($ch);

```

```javascript
//javascript code pending
```

> The above command returns JSON structured like this:

```json
  { 
    "data": {
      "entity_type": "Player",
      "entity_id": 1,
      "last_updated_at_unix": 1516747617,
      "generated_at_unix": 1516751509,
      "first_name": "John",
      "last_name": "Smith",
      "gender": "Male",
      "bio": "John is a professional bowler with a handicap of XYZ",
      "average_score": 201.2,
      "games": [
        {
          "individual_score": 130.0,
          "record_url": "https://samplebowlingapi.com/api/v1/games/1"
        },
        {
          "individual_score": 130.0,
          "record_url": "https://samplebowlingapi.com/api/v1/games/2"
        },
      ]
    },
  }
```

This endpoint retrieves a specific player.


### HTTP Request

`GET https://samplebowlingapi.com/api/v1/players/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the player to retrieve


### Fields Returned

Field | Type | Description
--------- | ------- | -----------
data | Object | Container object for all entity data
entity_type | String | Entity/Record type
entity_id | Integer | Unique ID for given entity type
first_name | String | First name of player
last_name | String | Last name of player
gender | String | Gender of player
bio | String | Biography of player
average_score | Decimal | Average score across all games for player
games | Array | Array of all game data for player


## Get All Players

```ruby
require 'open-uri'

url = "https://samplebowlingapi.com/api/v1/players"

data = open(url).read
```

```python
#python code pending
```

```php

$ch = curl_init("https://samplebowlingapi.com/api/v1/players");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HEADER, 0);
$data = curl_exec($ch);
curl_close($ch);

```

```javascript
//javascript code pending
```

<!--
> Make sure to replace `your_api_key` with your API key.
-->


This endpoint retrieves all players.

### HTTP Request

`GET https://samplebowlingapi.com/api/v1/players`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
ids | [] | If set to array of IDs, will return specific players requested
limit | 20 | Limit of players returned for each request

<!--
<aside class="success">
Remember — each request must contain your personal API key.
</aside>
-->


# Games

## Create a Game

```ruby
require 'rest-client'

url = "https://samplebowlingapi.com/api/v1/games"

response = RestClient.post url, {name: 'Game of the Century'}

data = response.body
```

```python
#python code pending
```

```php

$ch = curl_init("https://samplebowlingapi.com/api/v1/games");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HEADER, 0);
$data = curl_exec($ch);
curl_close($ch);

```

```javascript
//javascript code pending
```

> The above command returns JSON structured like this:

```json
  {
  "data": {
    "entity_type": "Game",
    "entity_id": 1,
    "status": "complete",
    "last_updated_at_unix": 1516747555,
    "generated_at_unix": 1516751945,
    "name": "Game of the Century",
    "start_date": "2018-01-01",
    "players": [
      {
        "record_url": "https://samplebowlingapi.com/api/v1/players/1",
        "entity_id": 1,
        "score": 120.0,
        "frames_completed": 10,
        "status": "complete"
      },
      {
        "record_url": "https://samplebowlingapi.com/api/v1/players/2",
        "entity_id": 1,
        "score": 120.0,
        "frames_completed": 10,
        "status": "complete"
      },
      {
        "record_url": "https://samplebowlingapi.com/api/v1/players/3",
        "entity_id": 1,
        "score": 120.0,
        "frames_completed": 10,
        "status": "complete"
      }
    ],
  }
}
```

This endpoint creates a game.


### HTTP Request

`POST https://samplebowlingapi.com/api/v1/games`

### URL Parameters


Parameter | Type | Description
--------- | ------- | -----------
name | String | The name of the game to be saved


### Fields Returned

Field | Type | Description
--------- | ------- | -----------
data | Object | Container object for all entity data
entity_type | String | Entity/Record type
entity_id | Integer | Unique ID for given entity type
name | String | Saved name of game
status | String | Game status (complete or active)
last_updated_at_unix | Integer | Unix timestamp when game last updated
start_date | String | Date when game was started
players | Array | Array of each player data for game


## Get a Specific Game

```ruby
require 'open-uri'

url = "https://samplebowlingapi.com/api/v1/games/1"

data = open(url).read
```

```python
#python code pending
```

```php

$ch = curl_init("https://samplebowlingapi.com/api/v1/games/1");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HEADER, 0);
$data = curl_exec($ch);
curl_close($ch);

```

```javascript
//javascript code pending
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "entity_type": "Game",
    "entity_id": 1,
    "status": "complete",
    "last_updated_at_unix": 1516747555,
    "generated_at_unix": 1516751945,
    "name": "Game of the Century",
    "start_date": "2018-01-01",
    "players": [
      {
        "record_url": "https://samplebowlingapi.com/api/v1/players/1",
        "entity_id": 1,
        "score": 120.0,
        "frames_completed": 10,
        "status": "complete"
      },
      {
        "record_url": "https://samplebowlingapi.com/api/v1/players/2",
        "entity_id": 1,
        "score": 120.0,
        "frames_completed": 10,
        "status": "complete"
      },
      {
        "record_url": "https://samplebowlingapi.com/api/v1/players/3",
        "entity_id": 1,
        "score": 120.0,
        "frames_completed": 10,
        "status": "complete"
      }
    ],
  }
}
```

This endpoint retrieves a specific game.


### HTTP Request

`GET https://samplebowlingapi.com/api/v1/games/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the game to retrieve

### Fields Returned

Field | Type | Description
--------- | ------- | -----------
data | Object | Container object for all entity data
entity_type | String | Entity/Record type
entity_id | Integer | Unique ID for given entity type
name | String | Saved name of game
status | String | Game status (complete or active)
last_updated_at_unix | Integer | Unix timestamp when game last updated
start_date | String | Date when game was started
players | Array | Array of each player data for game


## Get All Games

```ruby
require 'open-uri'

url = "https://samplebowlingapi.com/api/v1/games"

data = open(url).read
```

```python
#python code pending
```

```php

$ch = curl_init("https://samplebowlingapi.com/api/v1/games");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HEADER, 0);
$data = curl_exec($ch);
curl_close($ch);

```

```javascript
//javascript code pending
```

<!--
> Make sure to replace `your_api_key` with your API key.
-->


This endpoint retrieves all games.

### HTTP Request

`GET https://samplebowlingapi.com/api/v1/games`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
ids | [] | If set to array of IDs, will return specific games requested
limit | 20 | Limit of games returned for each request


# Frames

## Submit/Update a frame score

```ruby
require 'rest-client'

url = "https://samplebowlingapi.com/api/v1/frames"

response = RestClient.post url, {player_id: 1, game_id: 1, frame: 3, throw_1: 6, throw_2: 4}

data = response.body
```

```python
#python code pending
```

```php

$ch = curl_init("https://samplebowlingapi.com/api/v1/frames");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HEADER, 0);
$data = curl_exec($ch);
curl_close($ch);

```

```javascript
//javascript code pending
```

> The above command returns JSON structured like this:

```json
  {
  "data": {
    "entity_type": "Frame",
    "entity_id": 1,
    "status": "complete",
    "last_updated_at_unix": 1516747555,
    "generated_at_unix": 1516751945,
    "throw_1": 4,
    "throw_2": 6,
    "throw_3": null,
    "frame_score": 10,
    "is_spare": "true",
    "is_strike": "false",
    "player":
      {
        "record_url": "https://samplebowlingapi.com/api/v1/players/1",
      },
    "game":
      {
        "record_url": "https://samplebowlingapi.com/api/v1/games/1"
      }
  }
}
```

This endpoint submits/updates a frame score for given player and game.


### HTTP Request

`POST https://samplebowlingapi.com/api/v1/frames`

### URL Parameters

Parameter | Type | Description
--------- | ------- | -----------
game_id | Integer | The unique identifier for a given game
player_id | Integer | The unique identifier for a given player
frame | Integer | The current frame of game (1-10) for which score is being submitted
throw_1 | Integer | Pins knocked down on first throw of frame
throw_2 | Integer | Pins knocked down on second throw of frame
throw_3 | Integer | Pins knocked down on third throw of frame (only allowed if frame 10)


### Fields Returned

Field | Type | Description
--------- | ------- | -----------
data | Object | Container object for all entity data
entity_type | String | Entity/Record type
entity_id | Integer | Unique ID for given entity type
status | String | Frame status (complete or active); complete if all balls thrown
throw_1 | Integer | Pins knocked down on first throw of frame
throw_2 | Integer | Pins knocked down on second throw of frame
throw_3 | Integer | Pins knocked down on third throw of frame (only allowed if frame 10)
frame_score | Integer | Final score for frame
is_spare | Boolean | Returns true if frame was spare
is_strike | Boolean | Returns true if frame was strike
player | Object | Player metadata
game | Object | Game metadata
