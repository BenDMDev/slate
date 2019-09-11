# Categories


## Intro

Categories are way of organising data for importing and storing on the server. Catagories can have either children themselves categories in a similar sense to a typical folder structure i.e a folder can contain a another folder, which itself could contain another folder. Categories can be made public or private, allowing them to be available to all users or just the user that created them.

## Get All Categories

```shell
curl -X GET -i 'http://127.0.0.1/api/v1/categories/all'
```

> Example JSON response

```json
{
  "categories": [{
    "_id": "5c4b46a9d7f45e23255caf12",
    "name": "shp",
    "creator": "5bb8c73b3445365debe32951",
    "path": "shp",
    "colour": "#468847",
    "__v": 25,
    "created": "2019-01-25T17:26:01.181Z",
    "children_layer_id": ["5c4b4779d7f45e23255caf13"],
    "children_category_id": [],
    "parent_id": "-1",
    "sharePolicy": "Public"
  }]
}
```

This endpoint retrieves all Categories.


### HTTP Request

`GET /api/v1/categories/all`



## Get Top Category

```shell

curl -X GET -i 'http://127.0.0.1/api/v1/categories/tops'

```

> Example JSON Response

```json
{
  "categories": [{
    "_id": "5c4b46a9d7f45e23255caf12",
    "name": "shp",
    "creator": "5bb8c73b3445365debe32951",
    "path": "shp",
    "colour": "#468847",
    "__v": 25,
    "created": "2019-01-25T17:26:01.181Z",
    "children_layer_id": ["5c4b4779d7f45e23255caf13"],
    "children_category_id": [],
    "parent_id": "-1",
    "sharePolicy": "Public"
  }]
}
```

This endpoint retrieves the Top Category


### HTTP Request

`GET /api/v1/categories/tops`

## Get a Specific Category

This endpoint retrieves a specific Category.


### HTTP Request

```shell
curl -X GET -i 'http://127.0.0.1/api/v1/categories/5c4b46a9d7f45e23255caf12'

```
> Example JSON response

```json
{
  "success": true,
  "category": {
    "_id": "5c4b46a9d7f45e23255caf12",
    "name": "shp",
    "creator": "5bb8c73b3445365debe32951",
    "path": "shp",
    "colour": "#468847",
    "__v": 25,
    "created": "2019-01-25T17:26:01.181Z",
    "children_layer_id": ["5c4b4779d7f45e23255caf13"],
    "children_category_id": [],
    "parent_id": "-1",
    "sharePolicy": "Public"
  }
}

```

`GET /api/v1/categories/{category_id}`

### URL Parameters

Parameter | Description
--------- | -----------
category_id | The ID of the Category to retrieve

## Get a Category by Share Policy

```shell
curl -X GET -i 'http://127.0.0.1/api/v1/categories/workspace/Public'
```
> Example JSON Response

```json
{
  "success": true,
  "categories": [{
    "_id": "5c4b46a9d7f45e23255caf12",
    "name": "shp",
    "creator": "5bb8c73b3445365debe32951",
    "path": "shp",
    "colour": "#468847",
    "__v": 25,
    "created": "2019-01-25T17:26:01.181Z",
    "children_layer_id": ["5c4b4779d7f45e23255caf13"],
    "children_category_id": [],
    "parent_id": "-1",
    "sharePolicy": "Public"
  }]
}
```

This endpoint retrieves all categories with the specified share policy

### HTTP Request

`GET /api/v1/categories/workspace/{share_policy}`

### URL Parameters

Parameter | Required | Options | Description
--------- | -------- | ------- | -----------
share_policy | True | Public, Private | The Share Policy of the categories to retrieve

<aside class="notice">Private will return all categories with a private share policy created by the current authenticated user</aside>


## Get Category Ancestor Details

```shell

curl -X GET -i 'http://127.0.0.1/api/v1/categories/ancestors/5c4b46a9d7f45e23255caf12'

```

```json

{
  "success": true,
  "ancestors": ["5c4b46a9d7f45e23255caf12"]
}

```

### HTTP Request

`GET /api/v1/categories/ancestors/{category_id}`



### URL Parameters

Parameter | Required | Description
--------- | ------- | -----------
category_id | true | Category ID to retrieve Ancestor IDs for


## Get Category Layer IDs

### HTTP Request

```shell
curl -X GET -i 'http://127.0.0.1/api/v1/categories/5c4b46a9d7f45e23255caf12/layers'

```
> Example JSON response

```json
{
  "success": true,
  "layers": ["5c4b4779d7f45e23255caf13"]
}

```


`GET /api/v1/categories/{category_id}/layers`


### URL Parameters

Parameter | Required | Description
--------- | ------- | -----------
category_id | true | Category ID to retrieve Layer IDs for

## Get Sub Categories

### HTTP Request

```shell
curl -X GET -i 'http://127.0.0.1/api/v1/categories/5c4b46a9d7f45e23255caf12/sub-categories'
```

>Example JSON response

```json
{
  "success": true,
  "subCategories": [{
    "_id": "5d7900cf08b4be5bf22b4e15",
    "name": "shp",
    "creator": "5bb8c73b3445365debe32951",
    "path": "shp",
    "colour": "#468847",
    "__v": 25,
    "created": "2019-01-25T17:26:01.181Z",
    "children_layer_id": [],
    "children_category_id": [],
    "parent_id": "-1",
    "sharePolicy": "Public"
  }]
}

```

`GET /api/v1/categories/{category_id}/sub-categories`


### URL Parameters

Parameter | Required | Description
--------- | ------- | -----------
category_id | true | Category ID to retrieve Sub Categories for

## Create New Category

```shell
curl -X POST
 -H 'Content-Type: application/x-www-form-urlencoded'
 -i 'http://127.0.0.1/category/create'
--data 'name=shp&parent_id=-1&sharePolicy=Public&colour=green'
```

> The above command returns JSON structured like this:

```json

{
  "success": true,
  "category": {
    "__v": 0,
    "name": "shp",
    "creator": "5bb9f7ccd4bdb80d9f68d11c",
    "path": "shp",
    "colour": "green",
    "_id": "5d5d587b2750101d8414e21a",
    "created": "2019-08-21T14:43:07.059Z",
    "children_layer_id": [],
    "children_category_id": [],
    "parent_id": "-1",
    "sharePolicy": "Public"
  },
  "name": "shp"
}

```

This endpoint allows the creation of a new category.


### HTTP Request

`POST /api/v1/categories`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
name | true | Category Name
parent_id | true | Category Parent ID
sharePolicy | true | Share Policy - Valid Options: Public, Private
colour | true | Colour as a hash Code



## Delete a Specific Category


This endpoint deletes a specific Category \(only if current authenticated user is the creator\)


### HTTP Request

```shell
curl -X DELETE -i 'http://127.0.0.1/api/v1/categories/5d79020c08b4be5bf22b4e8a'
```

>Example JSON response

```json
{
  "success": true,
  "category_id": "5d79020c08b4be5bf22b4e8a"
}
```

`DELETE /api/v1/categories/{category_id}`

### URL Parameters

Parameter | Description
--------- | -----------
category_id | The ID of the Category to delete

## Delete all Empty Categories

```shell
curl -X DELETE -i 'http://127.0.0.1/api/v1/categories/empty'
```
>Example JSON Response

```json
{
  "success": true,
  "removed_category_ids": ["5d7900cf08b4be5bf22b4e15"]
}

```

This endpoint deletes empty Categories \(those without any sub-categories or layers\)


### HTTP Request

`DELETE /api/v1/categories/empty`
