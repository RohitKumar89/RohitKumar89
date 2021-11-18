<h2>NAGP Microservices Assignment- UrbanClap Application</h2>

UrbanClap Application for managing products and shopping lists using:

Spring Boot: Framework for creating standalone Java applications.<br/>
Netflix Zuul: API gateway.<br/>
Netflix Eureka: Service discovery.<br/>
RabbitMQ: Message broker.<br/>
H2 Database: H2 database based.<br/>

This application will consists of four different services:

<b>Product Service:</b> Provides API for managing available products ex- UrbanClap Home Services or Salon Services. By default it runs on port 8001.<br/>
<b>Order Service:</b> Provides API for managing shopping lists. By default it runs on port 8002.<br/>
<b>Admin Service:</b> Provides API for managing shopping lists. By default it runs on port 8002.<br/>
<b>Worker Service:</b> Provides API for managing shopping lists. By default it runs on port 8002.<br/>
<b>Payment Service:</b> Provides API for managing shopping lists. By default it runs on port 8002.<br/>
<b>Rating Service:</b> Provides API for managing shopping lists. By default it runs on port 8002.<br/>
<b>Service discovery:</b> Netflix Eureka service that discovers and registers other service instances. By default it runs on port 8761.<br/>
<b>API gateway:</b> Netflix Zuul API gateway that sits on the top of the product and shopping list services, providing a gateway for those services. By default it runs on port 8765.</br>

See the diagram below:

Architecture diagram

External services
This application depends on external services that must be up and running before attempting to run the application:

MongoDB
Shopping and product services use MongoDB for persistence, but different databases are used for each service.

Before running the application, ensure that you have a MongoDB instance running on localhost port 27017 (default port). The product and shopping-list databases will be created by the application if they don't exist.

RabbitMQ
RabbitMQ is used as message broker for communication between the services. When a product is deleted, a message is produced by the product service. This message contains details about the product that has been deleted. The shopping list service consumes the message and removes the deleted product from the shopping lists.

Before running the application, ensure that a RabbitMQ instance is running on localhost port 5672 (default port).

Building and running this application
To build and run this application, follow these steps:

Open a command line window or terminal.
Navigate to the root directory of the project, where the pom.xml resides.
Compile the project: mvn clean compile.
Package the application: mvn package.
Change into the target directory of the dist module: cd dist/target.
You should see a folder with the following or a similar name: microservices-1.0. Change into this folder: cd microservices-1.0.
Start the services as indicated below (the order doesn't matter).
Running the service discovery application
Open a command line window or terminal.
Start the service-discovery application: java -jar service-discovery-1.0.jar.
A Netflix Eureka console will be available at http://localhost:8761.
Running the product service application
Open a command line window or terminal.
Start the product-service application: java -jar product-service-1.0.jar.
This service will start on the port 8001 and it will automatically register itself in the service discovery. Check the Eureka console.
Running the shopping list service application
Open a command line window or terminal.
Start the shopping-list-service application: java -jar shopping-list-service-1.0.jar.
This service will start on the port 8002 and it will automatically register itself in the service discovery. Check the Eureka console.
Running the API gateway application
Open a command line window or terminal.
Start the api-gateway application: java -jar api-gateway-1.0.jar.
Running extra instances (optional)
If you want to, you can run extra instances of product-service and shopping-list-service applications, just use a different port: java -DPORT=8003 -jar product-service-1.0.jar. New instances will automatically register themselves in the service discovery.

Requests coming from the api-gateway service will be balanced between the instances.


<!---
RohitKumar89/RohitKumar89 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
