# Categories

## Get All Categories

> The above command returns JSON structured like this:

```json
{"name":"shp"}
```

This endpoint retrieves all Categories.

TO REPLACE: /getCategories

### HTTP Request

`POST /api/v1/categories/all`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
admin | true | Admin username
adminPassword | true | Admin password

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

TO REPLACE /create

### HTTP Request

`POST /api/v1/categories`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
name | true | Category Name
parent_id | true | Category Parent ID
sharePolicy | true | Share Policy - Valid Options: Public, Private
colour | true | Colour

## Get Top Category

> The above command returns JSON structured like this:

```json
{
  "_id": "5c4b46a9d7f45e23255caf12",
  "name": "shp",
  "creator": "5bb8c73b3445365debe32951",
  "path": "shp",
  "colour": "#468847",
  "__v": 1,
  "created": "2019-01-25T17:26:01.181Z",
  "children_layer_id": ["5c4b4779d7f45e23255caf13"],
  "children_category_id": [],
  "parent_id": "-1",
  "sharePolicy": "Public"
}
```

This endpoint retrieves the Top Category

TO REPLACE: /getTopCategory

### HTTP Request

`GET /api/v1/categories/top`

## Get a Specific Category

This endpoint retrieves a specific Category.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET /api/v1/categories/{category_id}`

### URL Parameters

Parameter | Description
--------- | -----------
category_id | The ID of the Category to retrieve

## Get a Category by Share Policy

This endpoint retrieves all categories with the specified share policy

TO REPLACE: /getAllPublicCategoies, /getUserPrivateCategories

### HTTP Request

`GET /api/v1/categories{?share_policy}`

### URL Parameters

Parameter | Required | Options | Description
--------- | -------- | ------- | -----------
share_policy | True | Public, Private | The Share Policy of the categories to retrieve

<aside class="notice">Private will return all categories with a private share policy created by the current authenticated user</aside>

## Get Category Ancestor Details

### HTTP Request

`POST /api/v1/categories/ancestor`

TO REPLACE: /getCategoryAncestorDetails

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
category_Ids | true | List of Category IDs to retrieve Ancestor details for

## Get Category Ancestor Details

### HTTP Request

`GET /api/v1/categories/{category_id}/ancestors`

TO REPLACE: /getCategoryAncestorIDs

### URL Parameters

Parameter | Required | Description
--------- | ------- | -----------
category_id | true | Category ID to retrieve Ancestor IDs for


## Get Category Layer IDs

### HTTP Request

`GET /api/v1/categories/{category_id}/layers`

TO REPLACE: /getCategoryLayersID

### URL Parameters

Parameter | Required | Description
--------- | ------- | -----------
category_id | true | Category ID to retrieve Layer IDs for

## Get Sub Categories

### HTTP Request

`GET /api/v1/categories/{category_id}/sub-categories`

TO REPLACE: /getSubCategories

### URL Parameters

Parameter | Required | Description
--------- | ------- | -----------
category_id | true | Category ID to retrieve Sub Categories for


## Delete a Specific Category


This endpoint deletes a specific Category.

TO REPLACE /remove

### HTTP Request

`DELETE /api/v1/categories/{category_id}`

### URL Parameters

Parameter | Description
--------- | -----------
category_id | The ID of the Category to delete