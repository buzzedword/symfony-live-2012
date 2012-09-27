Speaker: Larry Garfield
# Symfony2 meets Drupal 8

## Track record
- Powers 2% of sites
- Explosive growth
- Large community
- Thousands of extensions

Issues:
- 11 years old
- Powered by PHP4

Solution:
- Kernel of drupal
  - HttpFoundation
  - Routing
  - EventDispatcher
- Steering as close to existing components as possible
- Extended HttpKernel

Impressions:
- Drupal drastically rewrote their loader to mimick symfony style and PHP5 standards.

## Routing
- Drupal has ~1000 routes, most admin routes
- NestedMatcher is nearly complete
  - Databse backed fit based algorithm
  - Multi-stage matcher, filter based
  - Configurable via DIC
  - will support mimetype based matching
  - tentative work on stand alone negotiation library
- Will be pushed upstream to Symfony CMF routing

## Dependency Injection
