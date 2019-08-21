# Categories

## Get All Categories

> The above command returns JSON structured like this:

```json
{"name":"shp"}
```

This endpoint retrieves all Categories.

TO REPLACE: /getCategories

### HTTP Request

`POST /api/v1/categories/`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
admin | true | Admin username
adminPassword | true | Admin password


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

`GET /api/v1/categories/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Category to retrieve

## Delete a Specific Category


This endpoint deletes a specific Category.

TO REPLACE /remove

### HTTP Request

`DELETE /api/v1/categories/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Category to delete