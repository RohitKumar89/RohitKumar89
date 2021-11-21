<h2>NAGP Microservices Assignment- UrbanClap Application</h2>

UrbanClap Application for managing products and shopping lists using:

Spring Boot: Framework for creating standalone Java applications.<br/>
Netflix Zuul: API gateway.<br/>
Netflix Eureka: Service discovery.<br/>
RabbitMQ: Message broker.<br/>
H2 Database: H2 database based.<br/>

This application will consists of four different services:

<b>Product Service:</b> Provides API for managing available products ex- UrbanClap Home Services or Salon Services. By default it runs on port 8001.<br/>

<ul class="endpoints" id="product-controller_endpoint_list" style="">

<td width="50%"><span class="model-signature"><div>    
</div></span></td>
<td class="headers">         
        </form>
        <div class="response" style="">
          <h4 class="curl">Curl</h4>
          <div class="block curl"><pre>curl -X GET --header 'Accept: application/json' 'http://localhost:8001/products'</pre></div>
          <h4 data-sw-translate="">Request URL</h4>
          <div class="block request_url"><pre>http://localhost:8001/products</pre></div>
          <h4 data-sw-translate="">Request Headers</h4>
          <div class="block request_headers"><pre>{<br>  "Accept": "*/*"<br>}</pre></div>
          <h4 data-sw-translate="">Response Body</h4>
          <div class="block response_body hljs json"><pre class="json"><code>[
  {
    "<span class="hljs-attr">id</span>": <span class="hljs-number">1</span>,
    "<span class="hljs-attr">name</span>": <span class="hljs-string">"Yoga Trainer"</span>,
    "<span class="hljs-attr">description</span>": <span class="hljs-string">"Yoga Training Service Provided By Best Industry Trainer"</span>,
    "<span class="hljs-attr">category</span>": <span class="hljs-string">"HOME"</span>,
    "<span class="hljs-attr">rating</span>": <span class="hljs-string">"FIVE"</span>
  },
  {
    "<span class="hljs-attr">id</span>": <span class="hljs-number">1</span>,
    "<span class="hljs-attr">name</span>": <span class="hljs-string">"Electrician"</span>,
    "<span class="hljs-attr">description</span>": <span class="hljs-string">"Best &amp; Budget Hire For Electrician"</span>,
    "<span class="hljs-attr">category</span>": <span class="hljs-string">"HOME"</span>,
    "<span class="hljs-attr">rating</span>": <span class="hljs-string">"FIVE"</span>
  },
  {
    "<span class="hljs-attr">id</span>": <span class="hljs-number">1</span>,
    "<span class="hljs-attr">name</span>": <span class="hljs-string">"Beautician"</span>,
    "<span class="hljs-attr">description</span>": <span class="hljs-string">"Best &amp; Budget Hire For Salon Services"</span>,
    "<span class="hljs-attr">category</span>": <span class="hljs-string">"OTHER"</span>,
    "<span class="hljs-attr">rating</span>": <span class="hljs-string">"FIVE"</span>
  }
]</code></pre></div>
          <h4 data-sw-translate="">Response Code</h4>
          <div class="block response_code"><pre>200</pre></div>
          <h4 data-sw-translate="">Response Headers</h4>
          <div class="block response_headers"><pre>{<br>  "connection": "keep-alive",<br>  "content-type": "application/json",<br>  "date": "Sun, 21 Nov 2021 11:42:35 GMT",<br>  "keep-alive": "timeout=60",<br>  "transfer-encoding": "chunked",<br>  "vary": "Origin, Access-Control-Request-Method, Access-Control-Request-Headers"<br>}</pre></div>
        </div>
      </div>
    </li>
  </ul>
</li></ul>


<b>Order Service:</b> Provides API for managing shopping lists. By default it runs on port 8002.<br/>

<div class="response" style="">
          <h4 class="curl">Curl</h4>
          <div class="block curl"><pre>curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
   "category": "HOME", \ 
   "description": "Need an Electrician", \ 
   "id": 1234, \ 
   "latitude": 24.5, \ 
   "longitude": 25.6, \ 
   "name": "Rohit Kumar", \ 
   "shippingAddress": "VasantKunj, Delhi" \ 
 }' 'http://localhost:8002/order-service/'</pre></div>
          <h4 data-sw-translate="">Request URL</h4>
          <div class="block request_url"><pre>http://localhost:8002/order-service/</pre></div>
          <h4 data-sw-translate="">Request Headers</h4>
          <div class="block request_headers"><pre>{<br>  "Accept": "*/*"<br>}</pre></div>
          <h4 data-sw-translate="">Response Body</h4>
          <div class="block response_body hljs json"><pre class="json"><code>{
  "<span class="hljs-attr">id</span>": <span class="hljs-number">1234</span>,
  "<span class="hljs-attr">name</span>": <span class="hljs-string">"Rohit Kumar"</span>,
  "<span class="hljs-attr">description</span>": <span class="hljs-string">"Need an Electrician"</span>,
  "<span class="hljs-attr">category</span>": <span class="hljs-string">"HOME"</span>,
  "<span class="hljs-attr">shippingAddress</span>": <span class="hljs-string">"VasantKunj, Delhi"</span>,
  "<span class="hljs-attr">latitude</span>": <span class="hljs-number">24.5</span>,
  "<span class="hljs-attr">longitude</span>": <span class="hljs-number">25.6</span>
}</code></pre></div>
          <h4 data-sw-translate="">Response Code</h4>
          <div class="block response_code"><pre>202</pre></div>
          <h4 data-sw-translate="">Response Headers</h4>
          <div class="block response_headers"><pre>{<br>  "connection": "keep-alive",<br>  "content-type": "application/json",<br>  "date": "Sun, 21 Nov 2021 15:08:56 GMT",<br>  "keep-alive": "timeout=60",<br>  "transfer-encoding": "chunked",<br>  "vary": "Origin, Access-Control-Request-Method, Access-Control-Request-Headers"<br>}</pre></div>
        </div>



<H2>Task Service:</H2> Provides API for creating and managing tasks for <b>Admin and Service Providers(Prfessional/Worker)<b>. When Order will be placed by <b>Consumer</b>
        Corresponding to that Order a task will be created in database and these tasks will be reflected to Admin and Admin will assign those tasks to respective     <b>Worker/Service Provider</b> By default it runs on port 8003.<br/>

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
