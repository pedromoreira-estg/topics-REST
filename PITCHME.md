#HSLIDE
#SOA
###Service Oriented Architecture

#HSLIDE
###Service Oriented Architecture

* design style for software.
* based on services.
* services carry out small functionality.
* reusable, decoupled and distributed services.


#HSLIDE
###Service Oriented Architecture
####Advantages
* Re-usability
 * assemblage small, self-contained, and loosely coupled pieces.
* Maintainability
 * independent and smaller pieces of software.
* reliability
* Location Independence
 * published into a directory

#HSLIDE
###Service Oriented Architecture
####Advantages (cont.)
* Improved Scalability and Availability
 * easy to deploy multiple instances
* Improved Software Quality
 * less redundancy
* Platform Independence
 * message based


#HSLIDE
###Service Oriented Architecture
####Disadvantages
* Increased Overhead
 * Every time a service interacts with another service, complete validation of input takes place. This increases the response time and increases machine load.
* Complex Service Management
 * Ensure that messages have been delivered in a timely manner. Lots of messages.
* High Investment Cost
 * Implementation of SOA requires a large initial investment (tech and human resources)

#HSLIDE
###Service Oriented Architecture

####SOA may not be recommended for:
* homogeneous applications
* with heavy data exchange and with complex state
* real time applications
* stand-alone applications

#HSLIDE
###Service Oriented Architecture
####SOAP and REST
* two different choices to implement a SOA.


 
#HSLIDE
###Service Oriented Architecture
####SOAP vs REST

#####SOAP 
* standard, rigid
* HTTP as transport protocol
* Own protocol
* XML (many tools, but slow and verbose)
* no cache
* exposes operations

#HSLIDE
###Service Oriented Architecture
####SOAP vs REST
#####REST
* an architectural style
* HTTP as application protocol
* build on top of HTTP
* different representation formats (JSON, XML, ...)
* cacheable (scalability and perceived performance)
* exposes resources (representations)


#HSLIDE
###Service Oriented Architecture
###SOAP vs REST
#####SOAP
 * maturity
 * complete specification
 * support conversational state management
 * transactions, security

#####REST 
 * ease of implementation
 * agility of the design
 * lightweight
 * better support in browsers


#HSLIDE
#REST

####**RE**presentational **S**tate **T**ransfer

#HSLIDE
### What is it?	

**REST** is an architectural style that defines a set of constraints that, when applied to the architecture of a distributed system, induce desirable properties like **loose coupling** and **horizontal scalability**.

**RESTful** web services are the result of applying these constraints to services that utilize web standards such as URIs, HTTP, XML, and JSON.

#HSLIDE
### What is it?	

**REST** is not a set of standards

* => may result slightly different implementations, but observing the same set of principles / constraints.

 
**RESTful** web services are the result of applying these constraints to services that utilize web standards such as URIs, HTTP, XML, and JSON.


#HSLIDE
### What is it?
* Architectural Style for distributed Hypermedia Systems

* Originally described by Roy Fielding in his PhD [dissertation] (http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)

* six architectural guiding principles (constraints)
 * note: different authors may present a different organizations of the same principles 	


#HSLIDE
###6 Guiding Principles of REST

* P1 Client–server
* P2 Stateless
* P3 Cacheable
* P4 Uniform interface 
* P5 Layered system
* P6 Code on demand (optional)

#HSLIDE
####Guiding Principles of REST

P1 **Client–server**

* Clients are not concerned with data storage and other logic.
* Servers do not concern about user interface.
* => clear portability of the clients.
* => servers are easier to scale.
* => servers and clients can be independently developed.

#HSLIDE
####Guiding Principles of REST

P2 **Uniform Interface**

* **P2.a)** **addressability** and **resource-based**: individual resources identified by URIs (Universal Resource Identifiers). Resources are decoupled from their representations (A JSON document representing a view over a database using some specific character encoding).
* **P2.b)** **representation oriented**:  Clients are able to manipulate resources from their representations (e.g. delete a record of the database).

#HSLIDE
####Guiding Principles of REST

P2 **Uniform Interface**

* **P2.c)** **self descriptive** messages are self-contained, and include the necessary data to process the message (e.g. mime type).
* **P2.d)** **Hypermedia as the Engine of Application State** (HATEOAS) 
 1.  Clients deliver state via body contents, query-string parameters, request headers and the requested URI (the resource name).
 1. Services deliver state to clients via body content, response codes, and response headers.
 1. (Hyper) Links to the resource or to related resources are provided.

#HSLIDE
####Guiding Principles of REST

P2 **Uniform Interface**

* When **REST** is used to design web services, the uniform interface is based on the constrained set of **HTTP** verbs.
* Across the web, there are few fundamental operations over resources. HTTP provides four methods (***verbs***) that map to that basic operations:

 * Retrieve a representation of a resource:`HTTP GET`
 * Create a new resource: `HTTP PUT` to a new URI, or `HTTP POST` to an existing URI
 * Modify an existing resource: `HTTP PUT` to an existing URI
 * Delete an existing resource: `HTTP DELETE`

#HSLIDE
####Guiding Principles of REST
P3 **Stateless**
 
* Requests must contain all of the information necessary to understand the request.
* => Requests cannot take advantage of any stored context on the server.
* => State is therefore kept entirely on the client.

* => Stateless applications are **easier to scale** (e.g. multiple servers)

* ***important notice*** stateless does not means that interaction cannot be stateful. Proper mechanisms may be used to transfer state with client requests (url-encoded parameters, information sent in headers, etc.) 

#HSLIDE
####Guiding Principles of REST
P4 **Cacheable**

* Cache policies must be included with responses.
* Clients are free to reuse cached data as it remains valid.

#HSLIDE
####Guiding Principles of REST
P5 **Layered System** or **Micro services**

* Layered architecture composed of hierarchical layers
* Components cannot “see” beyond the immediate layer with which they are interacting.
* Layered systems reduce coupling across multiple layers by hiding the inner layers from all except the adjacent outer layer.
 * => improving evolvability and re-usability.
* example : client cannot ordinarily tell whether it is connected directly to the end server, or to an intermediary along the way.
 * Intermediary servers may improve system scalability by enabling load-balancing and by providing shared caches. 
 * Layers may also enforce security policies.

#HSLIDE
####Guiding Principles of REST
P6 **Code on demand (optional)**

* REST allows client functionality to be extended by downloading and executing code in the form of applets or scripts. 
* This simplifies clients by reducing the number of features required to be pre-implemented.
* Example: javascript code provided with a response.

#HSLIDE
####HTTP
* HTTP : HyperText Transfer Protocol
* Request-Response Protocol
* supports the World Wide Web
* many verbs : `GET`, `PUT`, `POST`, `DELETE`, `OPTIONS`, ...

#HSLIDE
####The Web : HTTP
A simple request (simplified)

```http
GET /posts/1 HTTP/1.1
Host: jsonplaceholder.typicode.com
Connection: keep-alive
Pragma: no-cache
User-Agent: Mozilla/5.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Encoding: gzip, deflate
```

and the response (simplified)

```
HTTP/1.1 200 OK
Date: Tue, 13 Dec 2016 23:08:58 GMT
Content-Type: application/json; charset=utf-8
Cache-Control: public, max-age=14400
Content-Encoding: gzip

{
  "userId": 1,
  "id": 1,
  //...
}

```

#HSLIDE
####URI
#####Resources

Anything that’s important enough to be referenced as a 
thing.

Something that can be stored on a computer and represented as a stream of bits (record in a database, result of computation, etc)

* a album with a list of photos
* a photo
* The next five prime numbers after 1024
* The sales numbers for 2016

#HSLIDE
####URI

` scheme:[//[user:password@]host[:port]][/]path[?query][#fragment]
`
* scheme : access protocol
* authority (optional) : user name and password
* host : registered name (dns) or IP address
* port (optional) : port needed if different from standard
* path : path to the resource (hierarchical)
* query (optional): attribute value pairs
* fragment (optional) : identifier to a secondary resource as a section (part) of a document. 

#HSLIDE
####The Web : HTTP : Methods

#####HTTP Methods (Verbs)

* **GET**
 * Safe, Idempotent, Cacheable  
* **PUT**
 * Idempotent
* **DELETE**
 * Idempotent
* **POST** 
* **HEAD**
 * Safe, Idempotent


#HSLIDE
#### REST and HTTP Verbs
#####HTTP Methods (Verbs) have semantics

* **GET**
 * retrieve a representation of a resource
* **PUT**
 * update a resource, sending a new representation
 * may also be used to create a resource
* **DELETE**
 * delete a resource identified by a URI
* **POST**
 * Create a new resource, in particular subordinate resources

#HSLIDE
#### REST and HTTP Verbs
#####HTTP Methods (Verbs) have semantics

typical RESTful API HTTP semantics and HTTP status codes

|Verb|/items|/items/{id}|
|:---|:---|:---|
|GET| 200 (OK)<br>list of customers| 200 (OK) <br> 404 (not found)|
|PUT| 404 (not found)| 200 (OK) <br> 204 (no content) <br> 404 (not found)|
|POST| 201 (created) <br> location header (redirection) <br> with link to new resource  | 404 (not found)|
|DELETE| 404 (not found)| 200 (OK) <br> 404 (not found)|

#HSLIDE
##Exercise 1
#### Example (Fake) API

* JSONPlaceHolder
 * `http://jsonplaceholder.typicode.com/`
* Software needed:
 * Postman (Google Chrome, Windows, MacOS app) 
 * `https://www.getpostman.com/`


#HSLIDE
##Exercise 2
#### Example (Fake) API

* install json-server
 * npm install -g json-server  
* design a json document to store simple school related info
 * programmes (cursos)
 * classes (turmas)
 * students (alunos)
* run a instance of json-server with the db.

#HSLIDE
##Exercise 3
#### Consume Example (Fake) API

* use jquery to consume REST API

#HSLIDE
##Exercise 3
#### Your Own API
Develop your own node REST API using:

* Node + Express + Mongo + Mongoose
or
* Node + Express + MySQL + Sequelize
