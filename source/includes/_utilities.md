# Utilities


## Intro

Replace http://127.0.0.1 with the IP address of your Server!

## Get All Utilities

```shell
curl -X GET -i 'http://127.0.0.1/api/v1/utilities'
```

> Example JSON response

```json
{
  "utilities": [{
    "_id": "5e15a3bb242a5c15a3255ac9",
    "postcode": "M1",
    "name": "Gas Station 102A",
    "type": "Gas",
    "classification": "Critical",
    "__v": 0,
    "dependencies": ["a1", "a2", "a3"]
  }, {
    "_id": "5e15ee9b665b2018d28f3c69",
    "postcode": "M1",
    "name": "Power Station 302",
    "type": "Electric",
    "classification": "Critical",
    "__v": 0,
    "dependencies": ["5e15a30f22dd6a15141e56e3"]
  }]
}
```

This endpoint retrieves all Utilities


### HTTP Request

`GET /api/v1/utilities`



## Get Utility by ID

This endpoint retrieves a specific Utility.


### HTTP Request

```shell
curl -X GET -i 'http://127.0.0.1/api/v1/utilities/5e15ee9b665b2018d28f3c69'

```
> Example JSON response

```json
{
  "utility": {
    "_id": "5e15ee9b665b2018d28f3c69",
    "postcode": "M1",
    "name": "Power Station 302",
    "type": "Electric",
    "classification": "Critical",
    "__v": 0,
    "dependencies": ["5e15a30f22dd6a15141e56e3"]
  }
}
```

`GET /api/v1/utilities/{utility_id}`

### URL Parameters

Parameter | Description
--------- | -----------
utility_id | The ID of the Building to retrieve


## Create New Utility

```shell
curl -X POST -H 'Content-Type: application/json' -i 'http://127.0.0.1/api/v1/utilities' --data ' {
    "postcode": "M1",
    "name": "Power Station 302",
    "type": "Electric",
    "classification": "Critical",
    "__v": 0,
    "dependencies": ["5e15a30f22dd6a15141e56e3"]
  }'

```

> The above command returns JSON structured like this:

```json
{
  "utility": {
    "__v": 0,
    "postcode": "M1",
    "name": "Power Station 302",
    "type": "Electric",
    "classification": "Critical",
    "_id": "5e15ee9b665b2018d28f3c69",
    "dependencies": ["5e15a30f22dd6a15141e56e3"]
  }
}
```

This endpoint creates a new utilities.


### HTTP Request

`POST /api/v1/utilities`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
name | true | Utility Name
type | true | Utility Type - Valid Options: Gas, Water, Electric, Communications
postcode | true | Postcode
classification | true | Utility Classification - Valid Options: Critical, Major, Minor



## Delete a Specific Utility


This endpoint deletes a specific Utility


### HTTP Request

```shell
curl -X DELETE -i 'http://127.0.0.1/api/v1/utilities/5e15a30f22dd6a15141e56e3'
```

>Example JSON response

```json
{
  "utility": {
    "_id": "5e15a30f22dd6a15141e56e3",
    "postcode": "M1",
    "name": "Gas Station 102A",
    "type": "Gas",
    "classification": "Critical",
    "__v": 0,
    "dependencies": []
  }
}
```

`DELETE /api/v1/utilities/{utility_id}`

### URL Parameters

Parameter | Description
--------- | -----------
utility_id | The ID of the utility to delete




