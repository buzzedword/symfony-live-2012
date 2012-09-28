Speaker: David Zuelke
# Designing HTTP Interfaces and RESTful Web Services

- Differences between SOAP and REST

Problems w/L0 API
- Always a POST
- Doesn't use HTTP auth
- Operation info is enclosed in the request ("getdetail")

### Level 0 in the *Richardson Maturity Model*:
Plain old XML over the wire in an RPC fashion

- Level 0 is not RESTful
- Level 1 (RPC)
- Level 2
  - Use HTTP verbs
  - GET (safe and idempotent)
  - POST (unsafe, not idempotent)
  - PUT & DELETE (unsafe, idempotent)
  - Use HTTP status codes to indicate result success


Don't use Level 0 or Level 1

### Roy Fielding
Architectural styles and the design of network based software architectures

## Rest Constraints
- Client-Server
- Stateless
- Cacheable
- Layered System
- Code on Demand (optional)
- _Uniform Interface_
  - A URL identifies a Resource
  - Methods perform operations on resources
  - The operation is implicit and not part of the URL
  - A hypermedia format is used to represent the data.
  - Link relations are used to navigate a service


## Designing an HTTP Interface

- Define your resources


### Good URLS
- http://www.acme.com/products/
- http://www.acme.com/products/?filter=cats&sort=desc
- http://www.acme.com/prdoucts/1234
- http://www.acme.com/products/1234/pictures/
- http://www.acme.com/products/1234/photos/?sort=latest
- http://www.acme.com/products/1234/photos/5678

URLs don't actually matter in a RESTful system, but its helpful to think in terms of
resources


- Use the resources

### Collection operations

- http://www.acme.com/products/
  - GET to retrieve a list of products
  - POST to create a new product
    - returns
      - 201 created
      -  Location: http://www.acme.com/products/1235

### Item Opetaions

- http://www.acme.com/products/1234
  - GET to retrieve
  - PUT to update
  - DELETE to delete. Duh.


## WWW
Hyperlinks have no tight coupling.
- Loosely coupled by design
- HTTP 404 embraces failure by design
  - more information != more friction
- no limits to scalability
- www is protocol-centric


### RESTful Services with uniform interface
- Identification of Resources (eg through URIs)
- Representations are conceptually seperate
- Manipulation through representations (ie they are complete)
- HATEOAS
  - Use links to allow clients to discover locations and operationms
  - Link relations are used to express the possible options
  - Clients do not need to know URLs, so they can change
  - The entire application workflow is abstracted, thus changeable
  - The hypermedia type itself could be versioned if necessary
  - No breaking of clients if the implementation is updated



#### Sidebar

- REpresentational State Transfer (just in case you missed that)
- application/xml and application/json are not hypermedia formats
- Don't let the server maintain client state (e.g. cookies)
- Twitter is not at all RESTful.
