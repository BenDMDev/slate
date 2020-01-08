# Demographics


## Intro

Replace http://127.0.0.1 with the IP address of your Server!

## Get All Demographics

```shell
curl -X GET -i 'http://127.0.0.1/api/v1/demographics'
```

> Example JSON response

```json
{
  "demographics": [{
    "_id": "5e15eab306f6e7159f259e5c",
    "postcode": "M1",
    "totalHealthNeeds": 1500,
    "totalMobilityNeeds": 5000,
    "totalElderly": 5000,
    "totalPopulation": 12000,
    "__v": 0
  }]
}
```

This endpoint retrieves all demographics


### HTTP Request

`GET /api/v1/demographics`



## Get Demographic by ID

This endpoint retrieves a specific demographic.


### HTTP Request

```shell
curl -X GET -H 'Content-Type: application/json' -i 'http://127.0.0.1/api/v1/demographics/5e15eab306f6e7159f259e5c'

```
> Example JSON response

```json
{
  "demographic": {
    "_id": "5e15eab306f6e7159f259e5c",
    "postcode": "M1",
    "totalHealthNeeds": 1500,
    "totalMobilityNeeds": 5000,
    "totalElderly": 5000,
    "totalPopulation": 12000,
    "__v": 0
  }
}
```

`GET /api/v1/demographics/{demographics_id}`

### URL Parameters

Parameter | Description
--------- | -----------
building_id | The ID of the Building to retrieve


## Create New Demographic

```shell
curl -X POST -H 'Content-Type: application/json' -i 'http://127.0.0.1/api/v1/demographics' --data '{
"postcode" : "M1",
"totalHealthNeeds" : 1500,
"totalMobilityNeeds" : 5000,
"totalPopulation" : 12000,
"totalElderly" : 5000
}'

```

> The above command returns JSON structured like this:

```json
{
  "demographic": {
    "__v": 0,
    "postcode": "M1",
    "totalHealthNeeds": 1500,
    "totalMobilityNeeds": 5000,
    "totalElderly": 5000,
    "totalPopulation": 12000,
    "_id": "5e15eab306f6e7159f259e5c"
  }
}

```

This endpoint creates a new Demographic.


### HTTP Request

`POST /api/v1/demographics`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
postcode | true | Postcode for catchment area
totalPopulation | true | Total population for Catchment Area
totalElderly | true | Total number of elderly people in catchment Area (>65 years)
totalMobilityNeeds | true | Total number of people with specific mobility needs
totalHealthNeeds | true | Total number of people with specific health needs



## Delete a Specific Demographic


This endpoint deletes a specific Demographic


### HTTP Request

```shell
curl -X DELETE -H 'Content-Type: application/json' -i 'http://127.0.0.1:3001/api/v1/demographics/5e15eab306f6e7159f259e5c'
```

>Example JSON response

```json
{
  "demographic": {
    "_id": "5e15eab306f6e7159f259e5c",
    "postcode": "M1",
    "totalHealthNeeds": 1500,
    "totalMobilityNeeds": 5000,
    "totalElderly": 5000,
    "totalPopulation": 12000,
    "__v": 0
  }
}
```

`DELETE /api/v1/demographics/{demographic_id}`

### URL Parameters

Parameter | Description
--------- | -----------
building_id | The ID of the Building to delete




