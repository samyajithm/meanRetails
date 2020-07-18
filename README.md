# meanRetails

A Simple MEAN.js E-Commerce Application 

## Table of Contents
- [Dependencies](README.md#dependencies)
- [Features](README.md#features)
- [Frontend to Backend Connection](README.md#frontend-to-backend-connection)
- [MongoDB connection](README.md#mongodb-connection)
- [Development server](README.md#development-server)
- [Demo](README.md#demo)

##Dependencies
 > ##### Frontend
 * Angular-Cli: 8.3.27
 * Typescript: 3.5.3
 * Node: 11.15.0
 * bootstrap: 4.5.0
 * [Angular Material: 8.2.3](https://www.npmjs.com/package/@angular/material)
 * [ngx-translate: 12.1.2](https://www.npmjs.com/package/@ngx-translate/core)
 * [ngx-toaster: 11.3.3](https://www.npmjs.com/package/ngx-toastr)
 
 > ##### Backend
  * Node: 12.16.2
  * [body-parser: 1.19.0](https://www.npmjs.com/package/body-parser)
  * [express: 4.17.1](https://www.npmjs.com/package/express)
  * [mongoose: 5.9.22](https://www.npmjs.com/package/mongoose)
  * [morgan: 1.10.0](https://www.npmjs.com/package/morgan) - For logging HTTP requests

##Features

> ##### Frontend
  * Home page with list of products.
  * Add items to Cart.
  * Hover over cart icon to view items in the cart.
  * Each item in cart will have a subtotal and grand total. On clicking checkout a mock of successful order is shown.
  * Cart icon show a badge with number of items in cart.
  * Mark items as Favorite.
  * Hover over Favorite icon to view wish list in a popover.
  * Clicking on links in footer will show route change and dummy pages.
  * Translation support is added for localization/Internationalization.
  * Toaster is added to let user know state of the action performed.
  * 'Quantity' key is considered as max number of quantity a product can be added to cart. A info toaster will be shown when it exceeds the limit and the product will not be added to cart.
  * State is maintained after the refresh.
  
> ##### Backend
  * Inventory Management with modules - Store, Products, Orders
  * Store module :-
        * Endpoint : /stores 
        * method: `GET`, `POST` , `DELETE`
        * Operations: Add, Fetch all, Remove Store
  * Products module :-
        * Endpoint : /products 
        * method: `GET`, `POST` , `DELETE`, `Patch`
        * Operations: Add, Fetch all, Fetch One, Update, Remove Product
  * Orders module :-
        * Endpoint : /orders 
        * method: `GET`, `POST` , `DELETE`
        * Operations: Create , Fetch all, Fetch One, Cancel Order
  
  * All the operations can be done by using API from this [Postman collection](https://documenter.getpostman.com/view/11998783/T1DiGg6m) 

  * Added products can be viewed in Frontend Application [ngCart](https://samyajithm.github.io/ngCart/shop) developed using Angular. Features available are listed in [Repo of ngCart](https://github.com/samyajithm/ngCart.git)
   
  > **Note**: Product is fetched by making actual api call to endpoint `/products` and the placing orders are just a mock in Frontend App


## Frontend to Backend Connection
  * Navigate to `environment.ts | environment.prod.ts` accordingly
  * Change the value of the server to instance uri of backend application
      * To run the backend app locally, clone the node.js app from [repo](https://github.com/samyajithm/ngShop.git) and follow the steps from Readme.md
      
      Sample server value in `environment` file
      ```typescript
        export const environment = {
          production: false,
          server: "http://localhost:3000"
        };         
      ```  
      * To connect to backend app hoisted in glitch online server (http://ngshop.glitch.me/products)
      
      Sample server value in `environment` file
      ```typescript
        export const environment = {
          production: false,
          server: "https://ngShop.glitch.me"
        };         
      ```  
      
## MongoDB connection 
* MongoDB Hoisted in MongoDB Atlas 
    * Connect to Application URI -(mongodb+srv://ngShop:ngShop@ngshop.0h5cq.mongodb.net/ngShop?retryWrites=true&w=majority)
    * Connect using Mongodb compass - (mongodb+srv://ngShop:ngShop@ngshop.0h5cq.mongodb.net/test) 
    * Connect with Mongo Shell - (mongo "mongodb+srv://ngshop.0h5cq.mongodb.net/<dbname>" --username ngShop)

* Config.json is used to provide db connection details
* Open `<project_folder>\server\config\config.json` and

> Sample Connection details for local db instance
```json
{
  "env": {
    "remoteDb": false,
    "dbHost": "127.0.0.1:27017/ngShop?retryWrites=true&w=majority",
    "dbUserName": "",
    "dbPassword": ""
  }
}
```
> Sample Connection details for remote db instance
```json
{
  "env": {
    "remoteDb": true,
    "dbHost": "@ngshop.0h5cq.mongodb.net/ngShop?retryWrites=true&w=majority",
    "dbUserName": "ngShop",
    "dbPassword": "ngShop"
  }
}
```  
## Development server

* Navigate to project base folder in your local system and Run `npm install`.
* `npm start` to start the angular and node.js application. This will start the angular application on port 4200 and node.js application on port 3000


## Demo 

* [Demo](https://samyajithm.github.io/ngCart/shop)
* [Postman Collection](https://documenter.getpostman.com/view/11998783/T1DiGg6m)

  > **# Note:** [Demo](https://samyajithm.github.io/ngCart/shop) instance is connected to node.js app hoisted in (http://ngshop.glitch.me) and MongoDb hoisted in MongoDB atlas.
  >> There will be a initial load time for the server to start in the hoisted environment. As it will be shut down due to inactivity.    Angular app will be showing the spinner
