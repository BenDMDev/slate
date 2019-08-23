# Layers

## Get All Layers

### HTTP Request

`GET /api/v1/layers/all`

## Create Layer

### HTTP Request

`POST /api/v1/layers`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
categoryId | true | ID for Parent Category
sharePolicy | true | Share Polic - Options: Public, Private
icon | true | Icon
type | true | Layer Type
clusterTextColor | true | Cluster Text Colour
customData | true | Custom Data
description | true | Description



## Get Layer by ID

### HTTP Request

`GET /api/v1/layers/{layer-id}`

## Get Layer by Category ID

### HTTP Request

`GET /api/v1/layers{?category-id}`


## Move Layer to new Category

### HTTP Request

`POST /api/v1/layers/{layer-id}`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
categoryId | true | New Category ID


## Check Owner

### HTTP Request

`GET /api/v1/layers/{layer-id}/user`

## Get Layer Info

### HTTP Request

`GET /api/v1/layers/{layer-id}/info`


## Delete Layer

### HTTP Request

`DELETE /api/v1/layers/{layer-id}`


