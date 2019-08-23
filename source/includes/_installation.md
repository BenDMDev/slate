# Installation

## Requirements

- MongoDB v4 
- NodeJS

## Linux

### Installing Node and NPM

- Either download the installer directly from the [NodeJS](https://nodejs.org/en/) Site Or...
- [Install](https://nodejs.org/en/download/package-manager/) via your preferred package manager (depending on the linux distro you're using)

<aside class="notice">The package manger npm is included by default with NodeJS</aside>


### Installing MongoDB

This project uses the NoSQL database MongoDB. This needs to be [installed](https://docs.mongodb.com/manual/installation/) and then ran before the node server can be started \(running without MongoDB will just result in a error\). 

MongoDB doesn't start initially on Linux \(unless ran as a service\). To start the MongoDB service running manually, use the following command.

`service mongod start` 

<aside class="notice">You may need to run this using sudo</aside>



## Windows 

### Installing Node and NPM

- Download the installer directly from the [NodeJS](https://nodejs.org/en/).


<aside class="notice">The package manger npm is included by default with NodeJS</aside>




### Installing MongoDB

This project uses the NoSQL database MongoDB. This needs to be [installed](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/) and then ran before the node server can be started \(running without MongoDB will just result in a error\). 

Assuming everything has gone correctly with the install wizard, the MongoDB service should start automatically on boot up.


## Starting Backend Service

<aside class="notice"> The following instructions apply to both Windows and Linux</aside>

Before running the backend service you will need to download the various dependencies used within the project. To this, open a terminal and change to the same directory where **package.json** is stored, run the following command.

`npm install`

This will install the various node dependencies for the project to run. You should now see a folder called node-modules within the project directory.

To start the node server running type the following command:

`npm run dev` OR `npm run start` 

<aside class="notice"> dev uses the development configuration and start uses the production configuration</aside>

By Default the server runs on localhost (127.0.0.1). 