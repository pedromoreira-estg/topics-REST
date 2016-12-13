#HSLIDE
#REST

####**RE**presentational **S**tate **T**ransfer




#HSLIDE
### What is it?
Architectural Style for distriibute Hypermedia Systems

Originally described by Roy Fielding in his PhD [dissertation] (http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)

6 guiding constraints


#HSLIDE
###6 Guiding Principles of REST

* Client–server
* Stateless
* Cacheable
* Uniform interface 
* Layered system
* Code on demand (optional)

#HSLIDE
####Guiding Principles of REST

P1 **Client–server**

* Clients are not concerned with data storage and other logic.
* Servers do not concern about user interface.
* client and servers communicate using an *uniform interface*.
* => clear portability of the clients.
* => servers are easier to scale.
* => servers and clients can be independently developed.


#HSLIDE
####Guiding Principles of REST

P2 **Uniform Interface**

* **addressability** individual resources identified by URIs (Universal Resource Identifiers)
* resources are decoupled from their representations (A JSON document representing a view over a database).
* clients are able to manipulate resources from their representations (e.g. delete a record of the database).
* self descriptive messages
* Hypermedia as the Engine of Application State (HATEOAS)
 *  Clients deliver state via body contents, query-string parameters, request headers and the requested URI(the resource name).
 * Services deliver state to clients via body content, response codes, and responseheaders.

#HSLIDE
####Guiding Principles of REST
P3 **Stateless**
 
* Requests must contain all of the information necessary to understand the request.
* => Requests cannot take advantage of any stored context on the server.
* => State is therefore kept entirely on the client.
* =>  

#HSLIDE
####Guiding Principles of REST
P4 **Cacheable**

* Cache policies must be included with responses.
* Clients are free to reuse cached data as it remains valid.

#HSLIDE
####Guiding Principles of REST
P5 **Layered System** or **Microservices**

* Layered architecture composed of hierarchical layers
* Components cannot “see” beyond the immediate layer with which they are interacting.
* Layered systems reduce coupling across multiple layers by hiding the inner layers from all except the adjacent outer layer.
 * => improving evolvability and reusability.
* example : client cannot ordinarily tell whether it is connected directly to the end server, or to an intermediary along the way. Mediate servers or API Gateways may improve system scalability by enabling  

#HSLIDE
####Guiding Principles of REST
P6 **Code on demand (optional)**

* REST allows client functionality to be extended by downloading and executing code in the form of applets or scripts. 
* This simplifies clients by reducing the number of features required to be pre-implemented.
* Example: javascript code provides with a response.