Speaker: Dustin Whittle
# Silex: From Micro To Full Stack

#### Note: this is a fast moving talk. Will be fewer notes.

What is silex?
- Micro framework based on Symfony components
- Requires 5.3.3+

Limitations
- No cli tool
- Any feature that requires mandatory external files
- TODO: grab others

Why Use?
- TODO: too fast

## App structure
- Single app structure
  - One front controller with routing functions
- composer enabled
- Bootstrap skeletons available
  - fabbot/silex-skeleton
    - just use it.
    - has symfony exception handling
- Holy crap, Dustin is coding on the fly. Repo to follow.
  - _https://github.com/dustinwhittle/Silex-SymfonyLive-2012_

## Adding features with providers
- Uses Pimple for a DIC
- Similar to bundles for Symfony

Core providers
- URL gen
- Session
- validator
- TODO: more listed

## Twig
- Register twig
- Set Path

## Translations
- Register trans
- set dictionary
- access `$app->translator`

## Forms
- register form service provider
- create form
  - uses a form factory service
  - form builder
    - add form fields
  - bind request to form
  - return form w/view

## Validation
- register validator
- register translator
- specify validation constraints
- assert constraints
- proceed as sf2

## Caching
- register httpcache
- set cache dir
- return response object w/cache headers

## Doctrine DBAL
Caveat: NOT the orm, if you need it, use SF2

- exposes a PDO object
- register doctrine provider
- set driver
- set path
- execute query

## JSON
- Silex "sweet spot"
  - if you need a simple JSON API, "use silex"
- Already has doctrine set up, just return JSON encoded data
  - uses routes and request objects to mutate the query

## Monolog
- register monolog
- set logfile
- write to log

## SwiftMailer
- register swiftmailer
- set swift message
- send message

## Security
CAVEAT: if you need security, you should be using SF2
- register security provider
- add firewall
  - set patterns
  - set routes
- fetch token


## What is a full stack framework?
- default structure
- default conventions
- configuration (yml, xml, ini, etc)
- sf2 you remove features
- silex you add them

## Scaling Silex for larger apps
- exposing new functionality w/service providers
- moving out of a single file
  - controllers in diff files
  - template files


## Considerations
Fabpot skeleton already has twig/silex helpers already registered

## Thoughts
Seems that Dustin has started with a stock Silex install. Through
using composer and fabpot's skeleton, he's slowly building up Silex to be
more full featured, and utilizes more of Symfony's underlying core. So far,
controller functions have been broken out into another file rather than in the
front matter. Exceptions have been brought over from Symfony as well.