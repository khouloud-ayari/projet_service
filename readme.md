API Gateway
This is the README file for the apiGateway.js file, which serves as the API Gateway for your application. The API Gateway is responsible for routing requests from clients to the appropriate services and handling the communication between the client and the underlying gRPC services.

Prerequisites
Before running the API Gateway, make sure you have the following dependencies installed:

Node.js (v10 or higher)
Express.js
Apollo Server
Body Parser
CORS
gRPC
Proto Loader
Installation
Clone the repository or download the source code containing the apiGateway.js file.

Navigate to the project directory in your terminal.

Run the following command to install the required dependencies:


npm install
Configuration
Before running the API Gateway, you need to configure the gRPC services and the port number for the API Gateway.

Open the apiGateway.js file in a text editor.

Modify the following lines to specify the paths to your gRPC proto files:


const productProtoPath = 'product.proto';
const orderProtoPath = 'order.proto';
Update the gRPC service URLs to match your service configurations:



const clientProducts = new productProto.ProductService('localhost:50051', grpc.credentials.createInsecure());
const clientOrders = new orderProto.OrderService('localhost:50052', grpc.credentials.createInsecure());
Optionally, you can change the port number for the API Gateway by modifying the following line:


const port = 3000;
Starting the API Gateway
To start the API Gateway, follow these steps:

Open a terminal and navigate to the project directory.

Run the following command:


node apiGateway.js
Once the API Gateway is running, you should see a message in the console indicating the port number:


API Gateway running on port 3000
Endpoints
Products
GET /products: Retrieve a list of all products.
GET /products/:id: Retrieve a product by ID.
POST /products: Create a new product.
PUT /products/:id: Update an existing product.
DELETE /products/:id: Delete a product.
Orders
GET /orders: Retrieve a list of all orders.
GET /orders/:id: Retrieve an order by ID.
POST /orders: Create a new order.
PUT /orders/:id: Update an existing order.
DELETE /orders/:id: Delete an order.
GraphQL Schema
The API Gateway exposes the following GraphQL schema:

graphql
Copy code
type Product {
  id: String!
  title: String!
  description: String!
}

type Order {
  id: String!
  title: String!
  description: String!
}

type Query {
  product(id: String!): Product
  products: [Product]
  order(id: String!): Order
  orders: [Order]
}

type Mutation {
  addProduct(id: String!, title: String!, description: String!): Product
  updateProduct(id: String!, title: String!, description: String!): Product
  deleteProduct(id: String!): Boolean
  addOrder(id: String!, title: String!, description: String!): Order
  updateOrder(id: String!, title: String!, description: String!): Order
  deleteOrder(id: String!): Boolean
}
Dependencies
express
@apollo/server
body-parser
cors
@grpc/grpc-js
@grpc/proto-loader
Configuration
The API Gateway requires the following gRPC service definitions:

product.proto: Protobuf definition for the ProductService.
order.proto: Protobuf definition for the OrderService.
Make sure to update the file paths in the apiGateway.js file to match the location of your gRPC service definitions.
API Endpoints
The API Gateway exposes the following endpoints for interacting with the gRPC services:

GET /products
Description: Retrieves a list of products.
Response: Returns a JSON array of products.
POST /product
Description: Creates a new product.
Request Body: Requires the following properties:
id: The ID of the product.
title: The title of the product.
description: The description of the product.
Response: Returns the created product as a JSON object.
GET /products/:id
Description: Retrieves a specific product by ID.
Request Parameter: Requires the id parameter to specify the ID of the product.
Response: Returns the product as a JSON object.
GET /orders
Description: Retrieves a list of orders.
Response: Returns a JSON array of orders.
POST /order
Description: Creates a new order.
Request Body: Requires the following properties:
id: The ID of the order.
title: The title of the order.
description: The description of the order.
Response: Returns the created order as a JSON object.
GET /orders/:id
Description: Retrieves a specific order by ID.
Request Parameter: Requires the id parameter to specify the ID of the order.
Response: Returns the order as a JSON object.
Conclusion
The API Gateway provides a unified interface for accessing the gRPC services related to products and orders. By starting the API Gateway and making requests to the defined endpoints, you can interact with the services and retrieve or create data as needed.
