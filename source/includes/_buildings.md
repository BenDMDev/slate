# Buildings


## Intro

Replace http://127.0.0.1 with the IP address of your Server!

## Get All Buildings

```shell
curl -X GET -i 'http://127.0.0.1/api/v1/buildings'
```

> Example JSON response

```json
{
  "building": {
    "__v": 0,
    "name": "Mac Court",
    "type": "Residential",
    "postcode": "M1 234",
    "city": "Manchester",
    "size_m2": 3000,
    "maxOccupants": 100,
    "value": 120000,
    "_id": "5e15b7f9d765fd60cdb5fc8e"
  }
}
```

This endpoint retrieves all Buildings


### HTTP Request

`GET /api/v1/buildings`



## Get Building by ID

This endpoint retrieves a specific Building.


### HTTP Request

```shell
curl -X GET -i 'http://127.0.0.1/api/v1/buildings/5c4b46a9d7f45e23255caf12'

```
> Example JSON response

```json
{
  "building": {
    "__v": 0,
    "name": "Mac Court",
    "type": "Residential",
    "postcode": "M1 234",
    "city": "Manchester",
    "size_m2": 3000,
    "maxOccupants": 100,
    "value": 120000,
    "_id": "5e15b7f9d765fd60cdb5fc8e"
  }
}
```

`GET /api/v1/buildings/{building_id}`

### URL Parameters

Parameter | Description
--------- | -----------
building_id | The ID of the Building to retrieve


## Create New Building

```shell
curl -X POST -H 'Content-Type: application/json' -i 'http://127.0.0.1:3001/api/v1/buildings' --data '{
"postcode" : "M1 234",
"type" : "Residential",
"name" : "Mac Court",
"maxOccupants" : 100,
"city" : "Manchester",
"size_m2" : 3000,
"value" : 120000
}'

```

> The above command returns JSON structured like this:

```json

{
  "building": {
    "__v": 0,
    "name": "Wetherspoons",
    "type": "Commercial",
    "postcode": "M1 234",
    "city": "Manchester",
    "size_m2": 3000,
    "maxOccupants": 100,
    "value": 120000,
    "_id": "5e15c8a24ef172660ea7ab4e"
  }
}

```

This endpoint creates a new Building.


### HTTP Request

`POST /api/v1/buildings`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
name | true | Building Name
city | true | Home City
type | true | Building Type - Valid Options: Residential, Commercial, Public, Education
postcode | true | Postcode
value | true | Value in £
maxOccupants | true | Max number of Occupants
area_m2 | true | floor area in Metres squared



## Delete a Specific Building


This endpoint deletes a specific Building


### HTTP Request

```shell
curl -X DELETE -i 'http://127.0.0.1/api/v1/buildings/5d79020c08b4be5bf22b4e8a'
```

>Example JSON response

```json
{
  "building": {
    "_id": "5e15b7f9d765fd60cdb5fc8e",
    "name": "Mac Court",
    "type": "Residential",
    "postcode": "M1 234",
    "city": "Manchester",
    "size_m2": 3000,
    "maxOccupants": 100,
    "value": 120000,
    "__v": 0
  }
}
```

`DELETE /api/v1/buidlings/{building_id}`

### URL Parameters

Parameter | Description
--------- | -----------
building_id | The ID of the Building to delete




