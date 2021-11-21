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

<li class="endpoint">  <ul class="operations">
    <li class="get operation" id="product-controller_getProductsUsingGET">
      <div class="heading">
        <h3>
          <span class="http_method">
          <a href="#!/product-controller/getProductsUsingGET" class="toggleOperation">get</a>
          </span>
          <span class="path">
          <a href="#!/product-controller/getProductsUsingGET" class="toggleOperation ">/products</a>
          </span>
        </h3>
        <ul class="options">
          <li>
          <a href="#!/product-controller/getProductsUsingGET" class="toggleOperation"><span class="markdown"><p>Get All Products </p>
</span></a>
          </li>
        </ul>
      </div>
      <div class="content" id="product-controller_getProductsUsingGET_content" style="">
          <div class="response-class">
            <h4><span data-sw-translate="">Response Class</span> (<span data-sw-translate="">Status</span> 200)</h4>
              <div class="markdown"><p>OK</p>
</div>
            <p><span class="model-signature"><div>
<div>
<ul class="signature-nav">
  <li><a class="description-link" href="#" data-sw-translate="">Model</a></li>
  <li><a class="snippet-link selected" href="#" data-sw-translate="">Example Value</a></li>
</ul>
<div>

<div class="signature-container">
  <div class="description" style="display: none;">
      <span class="strong">Inline Model [</span><div>object</div><span class="strong">]</span>
  </div>

  <div class="snippet" style="display: block;">
      <div class="snippet_json" style="display: block;">
        <pre><code class="hljs json">[
  {}
]</code></pre>
        
      </div>
  </div>
</div>
</div></div></div></span></p>
            <br>
            <div class="response-content-type"><div><label data-sw-translate="" for="rct0.35489075475695775">Response Content Type</label>
<select name="responseContentType" id="rct0.35489075475695775">
  <option value="*/*">*/*</option>
</select>
</div></div>
            </div>


        <form accept-charset="UTF-8" class="sandbox">
          <div style="margin:0;padding:0;display:inline"></div>
          <div style="margin:0;padding:0;display:inline"></div>
          <h4 data-sw-translate="">Response Messages</h4>
          <table class="fullwidth response-messages">
            <thead>
            <tr>
              <th data-sw-translate="">HTTP Status Code</th>
              <th data-sw-translate="">Reason</th>
              <th data-sw-translate="">Response Model</th>
              <th data-sw-translate="">Headers</th>
            </tr>
            </thead>
            <tbody class="operation-status">
            <tr><td width="15%" class="code">401</td>
<td class="markdown"><p>Unauthorized</p>
</td>
<td width="50%"><span class="model-signature"><div>    
</div></span></td>
<td class="headers">
  <table>
    <tbody>
    </tbody>
  </table>
</td></tr><tr><td width="15%" class="code">403</td>
<td class="markdown"><p>Forbidden</p>
</td>
<td width="50%"><span class="model-signature"><div>    
</div></span></td>
<td class="headers">
  <table>
    <tbody>
    </tbody>
  </table>
</td></tr><tr><td width="15%" class="code">404</td>
<td class="markdown"><p>Not Found</p>
</td>
<td width="50%"><span class="model-signature"><div>    
</div></span></td>
<td class="headers">
  <table>
    <tbody>
    </tbody>
  </table>
</td></tr></tbody>
          </table>
          <div class="sandbox_header">
            <input class="submit" type="submit" value="Try it out!" data-sw-translate="">
            <a href="#" class="response_hider" style="" data-sw-translate="">Hide Response</a>
            <span class="response_throbber" style="display: none;"></span>
          </div>
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
