# projet_service
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


/*
 * README.md
 * 
 * API Gateway
 * 
 * This API Gateway is responsible for routing requests to the appropriate gRPC services for the articles and books entities.
 * It uses Apollo Server for GraphQL functionality and communicates with the gRPC services using proto-loader and @grpc/grpc-js.
 * 
 * Prerequisites:
 * 1. Make sure the gRPC services for articles and books are running on the specified ports (50051 and 50052 respectively).
 * 2. Install the required dependencies by running `npm install`.
 * 
 * How to run:
 * 1. Run `node app.js` to start the API Gateway.
 * 2. The API Gateway will be running on port 3000.
 * 
 * Routes:
 * 1. GET /articles - Fetches all articles.
 * 2. POST /articles - Creates a new article.
 * 3. GET /articles/:id - Fetches the article with the specified ID.
 * 4. PUT /articles/:id - Updates the article with the specified ID.
 * 5. DELETE /articles/:id - Deletes the article with the specified ID.
 * 6. GET /books - Fetches all books.
 * 7. POST /books - Creates a new book.
 * 8. GET /books/:id - Fetches the book with the specified ID.
 * 9. PUT /books/:id - Updates the book with the specified ID.
 * 10. DELETE /books/:id - Deletes the book with the specified ID.
 * 
 * Make sure to replace 'localhost' with the appropriate host address if the gRPC services are running on a different machine.
 * 
 * Example usage:
 * 1. To fetch all articles, send a GET request to http://localhost:3000/articles.
 * 2. To create a new article, send a POST request to http://localhost:3000/articles with the article data in the request body.
 * 3. To fetch a specific article, send a GET request to http://localhost:3000/articles/:id, replacing :id with the article ID.
 * 4. To update a specific article, send a PUT request to http://localhost:3000/articles/:id with the updated article data in the request body.
 * 5. To delete a specific article, send a DELETE request to http://localhost:3000/articles/:id, replacing :id with the article ID.
 * 6. The same operations can be performed for books using the /books routes.
 * 
 */
