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
- Drupal has a lot of globals
  - Migrating to use injection container
- Currently used to check if global, else use DIC.

## Event dispatcher
Drupal 7

Benefits
- Like event dispatcher but uses function_exists() for registration
- Used for procedural AOP
- Faster than EventDispatcher
- No need to compile

Limitations
- No class autoloading
- Hard to unit test
- Only one of each hook per module

Drupal 8
- Will have both EventDispatcher and Hooks
- EventDispatcher closer to the core, Hooks further out
- Refactor hook engine to not be completely global for testing

Drupal 9
- Just eventDispatcher?

## Twig
Drupal 7
- PHP as tempalate language
- Array based rendering, defer rendering until the last possible moment
- Powerful preprocessing/filtering

Benefits
- Extremely flexible
- No need to compile templates
- On ramp for front-end developers to become PHP developers
- "All template languages eventually evolve to become Turing Complete"

Drawbacks
- Extremely opaque
- Unpredictable
- Front-end need to become PHP devs

Drupal 8
- MAYBE

Benefits
- More secure
- More front-end developer friendly
- Twig.js
- Not drupal-proprietary

Drawbacks
- Extremely different model makes transition difficult

## Replace NIH with PIE
"Proudly Invented Elsewhere"

- YAML component for config
- Doctrine common annotations
- Partial composer usage

Considering
- Assetic (meh)
- Guzzle (HTTP requests)
- Imagine (image handling)

## Refactors
- PSR-0
- Gettext
- PhpStorage
- Archiver
- Graph
- Plugin
- Reflection

## Collaboration
Licenses
- SF2: MIT
- Drupal: GPL

Drupal added:
- New Flash messaging API
- File Streaming -- 2.2
- Response::prepare() chaining
- Improve FlattenException
- UTF-8 encoding weirdness in JSON
- Allow routing matching on a full Request
- Make RouteCollection countable
- Imrpove route serialization
- TODO: missing item. Please fill?

