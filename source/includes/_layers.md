# Layers

## Intro

Layers represent some data imported by the user - such as a CSV, SHP or GeoJSON. They're a child node to a Category in a similar sense to tree like file structure - i.e Layers are the files, Categories are the folders.
Layers can be made public or private, allowing them to be available to all users or just the user that created them.  

## Get Layers 

Returns all public Layers and Private layers created by the current authenticated user

### HTTP Request

`GET /api/v1/layers`

```shell
curl -X GET 
-H 'Content-Type: application/x-www-form-urlencoded' 
-i 'http://127.0.0.1/api/v1/layers'
```

> Example JSON response

```json
[{
  "_id": "5c4b4779d7f45e23255caf13",
  "Title": "man_wards",
  "Category": "shp",
  "Category_id": "5c4b46a9d7f45e23255caf12",
  "sharePolicy": "Public",
  "Icon": "img/shapeImages/5bb8c73b3445365debe329511548437369690.png",
  "Type": "GeoJSON",
  "clusterTextColor": "",
  "CustomData": "",
  "description": "",
  "URL": "data/layers/15484373698305bb8c73b3445365debe32951.GeoJSON",
  "creator": "5bb8c73b3445365debe32951",
  "__v": 0,
  "created": "2019-01-25T17:29:29.831Z"
}]

```

## Get All Layers

Returns all layers (Admin Use Only)

### HTTP Request

`GET /api/v1/layers/all`

```shell
curl -X GET 
-H 'Content-Type: application/x-www-form-urlencoded' 
-i 'http://127.0.0.1/api/v1/layers/all'
```

> Example JSON response

```json
[{
  "_id": "5c4b4779d7f45e23255caf13",
  "Title": "man_wards",
  "Category": "shp",
  "Category_id": "5c4b46a9d7f45e23255caf12",
  "sharePolicy": "Public",
  "Icon": "img/shapeImages/5bb8c73b3445365debe329511548437369690.png",
  "Type": "GeoJSON",
  "clusterTextColor": "",
  "CustomData": "",
  "description": "",
  "URL": "data/layers/15484373698305bb8c73b3445365debe32951.GeoJSON",
  "creator": "5bb8c73b3445365debe32951",
  "__v": 0,
  "created": "2019-01-25T17:29:29.831Z"
}]
```

## Get Layer by ID

Returns a Layer based on the specified ID

### HTTP Request

`GET /api/v1/layers/{layer-id}`

```shell
curl -X GET 
-H 'Content-Type: application/x-www-form-urlencoded' 
-i 'http://127.0.0.1/api/v1/layers/5c4b4779d7f45e23255caf13'

```

> Example JSON response

```json

{
  "success": true,
  "layer": {
    "_id": "5c4b4779d7f45e23255caf13",
    "Title": "man_wards",
    "Category": "shp",
    "Category_id": "5c4b46a9d7f45e23255caf12",
    "sharePolicy": "Public",
    "Icon": "img/shapeImages/5bb8c73b3445365debe329511548437369690.png",
    "Type": "GeoJSON",
    "clusterTextColor": "",
    "CustomData": "",
    "description": "",
    "URL": "data/layers/15484373698305bb8c73b3445365debe32951.GeoJSON",
    "creator": "5bb8c73b3445365debe32951",
    "__v": 0,
    "created": "2019-01-25T17:29:29.831Z"
  }
}

```

## Get Layer by Category ID

Returns an array of layers with the specified Category ID

### HTTP Request

`GET /api/v1/layers/category/{category-id}`

```shell

curl -X GET 
-H 'Content-Type: application/x-www-form-urlencoded' 
-i 'http://127.0.0.1/api/v1/layers/category/5c4b46a9d7f45e23255caf12'

```
5d78ceb71478c60e261d197a

```json
{
  "success": true,
  "resultLayers": [{
    "_id": "5c4b4779d7f45e23255caf13",
    "Title": "man_wards",
    "Category": "shp",
    "Category_id": "5c4b46a9d7f45e23255caf12",
    "sharePolicy": "Public",
    "Icon": "img/shapeImages/5bb8c73b3445365debe329511548437369690.png",
    "Type": "GeoJSON",
    "clusterTextColor": "",
    "CustomData": "",
    "description": "",
    "URL": "data/layers/15484373698305bb8c73b3445365debe32951.GeoJSON",
    "creator": "5bb8c73b3445365debe32951",
    "__v": 0,
    "created": "2019-01-25T17:29:29.831Z"
  }]
}

```

## Create Layer

Create a new Layer 

### HTTP Request

`POST /api/v1/layers`

```shell
curl -X POST 
-H 'Content-Type: application/x-www-form-urlencoded' 
-i 'http://127.0.0.1/api/v1/layers/' 
--data 'categoryId=5c4b46a9d7f45e23255caf12&title='\''test_layer&sharePolicy=Public&icon=icon&type=csv&clusterTextColor=#FF0000&customData='\''custom data test'\''&description='\''test layer desc'\''&URL=test url'\''

```
>Example JSON Response

```json

{
  "success": true,
  "layer": {
    "__v": 0,
    "Title": "'test_layer",
    "Category": "shp",
    "Category_id": "5c4b46a9d7f45e23255caf12",
    "sharePolicy": "Public",
    "Icon": "icon",
    "Type": "csv",
    "clusterTextColor": "#FF0000",
    "CustomData": "'custom data test'",
    "description": "'test layer desc'",
    "URL": "data/layers/15681976766025bb9f7ccd4bdb80d9f68d11c.csv",
    "creator": "5bb9f7ccd4bdb80d9f68d11c",
    "_id": "5d78cc2c1478c60e261d1978",
    "created": "2019-09-11T10:27:56.605Z"
  }
}

```


### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
categoryId | true | ID for Parent Category
sharePolicy | true | Share Polic - Options: Public, Private
icon | true | Icon
type | true | Layer Type
clusterTextColor | true | Cluster Text Colour \(using # code\)
customData | true | Custom Data
description | true | Description


## Update Layer 

Update layer 

### HTTP Request

`PATCH /api/v1/layers/{layer-id}`

```shell

curl -X PATCH -H 'Content-Type: application/x-www-form-urlencoded' 
-i 'http://127.0.0.1/api/v1/layers/5d78ceda1478c60e261d197b' 
--data 'category_id=5d78ceb71478c60e261d197a

```
>Exmaple JSON Response

```json

{    
 "success": true,
 "oriCategory": "5c4b46a9d7f45e23255caf12"
}

```

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
categoryId | true | New Category ID


## Check Owner

Check if layer is owned by the current authenticated user

### HTTP Request

`GET /api/v1/layers/{layer-id}/user`

```shell
curl -X 
GET -H 'Content-Type: application/x-www-form-urlencoded' 
-i 'http://127.0.0.1/api/v1/layers/5c4b4779d7f45e23255caf13/user'

```
>Example JSON response

```json
{
  "success": true,
  "isOwner": false
}

```


## Get Layer Info

Return info about the specified layer ID

### HTTP Request

`GET /api/v1/layers/{layer-id}/info`

```shell

```
>Example JSON response

```json
{
  "success": true,
  "message": {
    "Title": "man_wards",
    "Category": "shp",
    "Description": "",
    "SharePolicy": "Public",
    "Type": "GeoJSON",
    "Icon": "img/shapeImages/5bb8c73b3445365debe329511548437369690.png",
    "Creator": "Kuo-Cheng Wu",
    "Created": "2019-01-25T17:29:29.831Z"
  }
}

```

## Delete Layer

Deletes layer matching the specified layer ID

### HTTP Request

`DELETE /api/v1/layers/{layer-id}`

```shell
curl -X DELETE 
-H 'Content-Type: application/x-www-form-urlencoded' 
-i 'http://127.0.0.1/api/v1/layers/5d78cdea1478c60e261d1979'

```

>Exmaple JSON Response

```json
{
  "success": true,
  "message": "'test_layer layer removed",
  "sharePolicy": "Public"
}

```

