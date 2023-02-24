<div align="center">
  <h1>Spill The Tea</h1>
  <img width="500" alt="Spill The Tea" src="https://media3.giphy.com/media/5hbX2MkyXqUGglr2kU/giphy.gif?cid=6104955emdratatd87dca1aw591eo0xvhnom265ox352w5th&rid=giphy.gif&ct=g">
</div

## Table of Contents

- [Project Overview](#project-overview)
- [Built With](#built-with)
- [Setup](#setup)

## Project Overview
A Tea Subscription Service

## Built With
- Rails 5.2.8
- Ruby 2.7.4

## Setup

1. Clone the repository
2. cd into the root directory
3. Install gem packages: `bundle install`
4. Setup the database: `rails db:{drop,create,migrate}`

## APIs

<details close>
<summary> customer </summary>
<br>

Request: <br>
```
GET /api/v1/customers/#{drake.id}/subscriptions
```

JSON Response Example:
```json
{
    "data": [
        {
            "id": "1",
            "type": "subscription",
            "attributes": {
                "tea_id": 1,
                "customer_id": 1,
                "title": "Spill the Tea",
                "price": 19.99,
                "frequency": "every_day",
                "status": "yay"
            }
        }
    ]
}
```
</details>

<details close>
<summary> new subscription </summary>
<br>

Request: <br>
```
POST /api/v1/customers/#{drake.id}/subscriptions
```

JSON Response Example:
```json
{
    "customer_id": 1,
    "tea_id": 1,
    "title": "Thai Tea",
    "price": "9.99",
    "frequency": "every_week",
    "status": "yay"
}
```
</details>

<details close>
<summary> update subscription </summary>
<br>

Request: <br>
```
PATCH "/api/v1/customers/#{drake.id}/subscriptions/#{subscription.id}?status=boo"
```

JSON Response Example:
```json
{
    "data": {
        "id": "2",
        "type": "subscription",
        "attributes": {
            "tea_id": 1,
            "customer_id": 1,
            "title": "Thai Tea",
            "price": 9.99,
            "frequency": "every_week",
            "status": "boo"
        }
    }
}
```
</details>
