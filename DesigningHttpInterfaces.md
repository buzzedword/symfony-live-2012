Speaker: David Zuelke
# Designing HTTP Interfaces and RESTful Web Services

- Differences between SOAP and REST

Problems w/API
- Always a POST
- Doesn't use HTTP auth
- Operation info is enclosed in the request ("getdetail")

### Level 0 in the *Richardson Maturity Model*:
Plain old XML over the wire in an RPC fashion

- Level 0 is not RESTful
- Level 1 (missed information)

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


#### Sidebar
REpresentational State Transfer (just in case you missed that)