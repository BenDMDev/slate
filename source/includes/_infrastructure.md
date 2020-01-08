# Infrastructure


## Intro

Replace http://127.0.0.1 with the IP address of your Server!

## Get All Infrastructure Entries

```shell
curl -X GET -i 'http://127.0.0.1/api/v1/infrastructure'
```

> Example JSON response

```json
{
  "infrastructure": [{
    "_id": "5e15ff5a1c7a63001279fb08",
    "type": "Road",
    "name": "M60 motorway",
    "classification": "Critical",
    "__v": 0,
    "postcodes": ["SK", "M", "OL", "WA"]
  }]
}
```

This endpoint retrieves all Infrastructure.


### HTTP Request

`GET /api/v1/infrastructure`




## Get Infrastructure by ID

This endpoint retrieves a specific Infrastructure Entry.


### HTTP Request

```shell
curl -X GET -i 'http://127.0.0.1/api/v1/infrastructure/5e15ff5a1c7a63001279fb08'

```
> Example JSON response

```json
{
  "infrastructure": {
    "__v": 0,
    "type": "Road",
    "name": "M60 motorway",
    "classification": "Critical",
    "_id": "5e15ff5a1c7a63001279fb08",
    "postcodes": ["SK", "M", "OL", "WA"]
  }
}
```

`GET /api/v1/infrastructure/{infrastructure_id}`

### URL Parameters

Parameter | Description
--------- | -----------
infrastructure_id | The ID of the Infrastructure to retrieve


## Create New Infrastructure Entry

```shell
curl -X POST -H 'Content-Type: application/json' -i 'http://127.0.0.1:3001/api/v1/infrastructure' --data '{
"areacodes" : ["M2", "M1", "M3"],
"type" : "Road",
"name" : "M60 Ring Road",
"classification" : "Critical"
}'
```

> The above command returns JSON structured like this:

```json

{
  "infrastructure": {
    "__v": 0,
    "type": "Road",
    "name": "M60 motorway",
    "classification": "Critical",
    "_id": "5e15ff5a1c7a63001279fb08",
    "postcodes": ["SK", "M", "OL", "WA"]
  }
}

```

This endpoint creates a new Infrastructure entry.


### HTTP Request

`POST /api/v1/infrastructure`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
name | true | Name of Infrastructure Entry
areacodes | false | Array of areacodes that road services
type | true | Infrastructure Type - Valid Options: Road, Rail, Airport, Port
classification | true | Infrastructure Classification - Valid Options: Critical, Major, Minor




## Delete a Specific Infrastructure entry


This endpoint deletes a specific Infrastructure entry


### HTTP Request

```shell
curl -X DELETE -H 'Content-Type: application/json' -i 'http://127.0.0.1:3001/api/v1/infrastructure/5e15cb81ee96906a87bf8bbd' --data '{
"areacodes" : ["M2", "M1", "M3"],
"type" : "Road",
"name" : "M60 Ring Road",
"classification" : "Critical"
}'
```

>Example JSON response

```json
{
  "infrastructure": {
    "__v": 0,
    "type": "Road",
    "name": "M60 motorway",
    "classification": "Critical",
    "_id": "5e15ff5a1c7a63001279fb08",
    "postcodes": ["SK", "M", "OL", "WA"]
  }
}
```

`DELETE /api/v1/infrastructure/{infrastructure_id}`

### URL Parameters

Parameter | Description
--------- | -----------
infrastructure_id | The ID of the Infrastructure Entry to delete




