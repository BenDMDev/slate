# Images

## Intro

Images represent user uploaded icons \(as well as default shapes/lines\) to use with the file structure of Categories/Layers. A custom image can be uploaded to represent certain layers, or a shape can be generated and stored on the server. 

## Upload Image

```shell
curl -X POST -H 'Content-Type: application/x-www-form-urlencoded' 
-i 'http://127.0.0.1/api/v1/images/' 
--data 'content='\''dummycontent'\''&filename='\''testContent.png'\'
```

```json
{
  "success": true,
  "message": "/res/customIcons/'testContent.png'"
}
```

Uploads an image to be stored on the server. 

### HTTP Request

`POST /api/v1/images/` 


## Create a Circle 

```shell
curl -X POST -H 'Content-Type: application/x-www-form-urlencoded' 
-i 'http://127.0.0.1/api/v1/images/circle'
--data 'color=#FF0000&filename=circle.png'
```

```json
{
  "success": true,
  "message": "/res/shapeImages/'circle.png'"
}

```

Create a circle with the specified color and save it to the server

### HTTP Request

`POST /api/v1/images/circle`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
color | true | Color as # Code
filename | true | filename to save shape as

## Create a Square

```shell

curl -X POST -H 'Content-Type: application/x-www-form-urlencoded' 
-i 'http://127.0.0.1/api/v1/images/square' 
--data 'color=#FF0000&boundary=#FF0000&filename=square.png'

```

```json

{
  "success": true,
  "message": "/res/shapeImages/square.png"
}

```

Create a square with the specified color and boundary and save to the server

### HTTP Request

`POST /api/v1/images/square`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
color | true | Color as # Code
boundary | true | Color for boundary of square as # code
filename | true | filename to save shape as

## Create a Line

```json

{
  "success": true,
  "message": "/res/shapeImages/line.png"
}


```

### HTTP Request

Create a line with the specified colour and width and save it to the server

`POST /api/v1/images/line`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
color | true | Color as # Code
width | true | Color for boundary of square as # code
filename | true | filename to save shape as
