# Layers

## Get Layers 

Returns all public Layers and Private layers created by the current authenticated user

### HTTP Request

`GET /api/v1/layers`

## Get All Layers

Returns all layers (Admin Use Only)

### HTTP Request

`GET /api/v1/layers/all`

## Get Layer by ID

Returns a Layer based on the specified ID

### HTTP Request

`GET /api/v1/layers/{layer-id}`

## Get Layer by Category ID

Returns an array of layers with the specified Category ID

### HTTP Request

`GET /api/v1/layers/category/{category-id}`


## Create Layer

Create a new Layer 

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


## Update Layer 

Update layer 

### HTTP Request

`PATCH /api/v1/layers/{layer-id}`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
categoryId | true | New Category ID


## Check Owner

Check if layer is owned by the current authenticated user

### HTTP Request

`GET /api/v1/layers/{layer-id}/user`

## Get Layer Info

Return info about the specified layer ID

### HTTP Request

`GET /api/v1/layers/{layer-id}/info`


## Delete Layer

Deletes layer matching the specified layer ID

### HTTP Request

`DELETE /api/v1/layers/{layer-id}`


