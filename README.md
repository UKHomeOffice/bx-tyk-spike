Tyk Spike

This project helps to bootstrap a simple Tyk installation, including dashboard.

1. Clone this project to a working directory.
1. From the working directory, run `docker-compose up`. This makes use of the docker-compose.yml file to start up a full Tyk installation, including redis, mongo, Tyk Pump, Tyk Dashboard and Tyk Gateway.
1. In Postman, import the Postman collection `dashboard/bootstrap poc user.postman_collection.json`.
1. Run this collection, making sure to tick the "keep variable values" option - this will set some environment variables useful for further API requests. After this, you should be able to log into the dashboard at http://localhost:3000 with email poc-user@default.com, password test123.

To make some sample API requests:
1. Import the [Petstore API Swagger definition](https://petstore.swagger.io/v2/swagger.json) to Postman - more API details [here](https://petstore.swagger.io/).
1. Have a look at the `GET /store/inventory` endpoint (or any endpoint) in Postman. Change the base URL so that it points to your local Tyk Gateway (should be running on http://localhost:8080). If you run the request, it won't work yet.
1. The Swagger petstore API has to be registered on the dashboard (http://localhost:3000). This can be done in the UI, or using the Tyk API. The target URL will be `https://petstore.swagger.io`.
1. If requiring authorization for the petstore API, keys for access can be managed in the Keys section of the UI, or using API endpoints.
