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

## Thoughts
Seems that Dustin has started with a stock Silex install. Through
using composer and fabpot's skeleton, he's slowly building up Silex to be
more full featured, and utilizes more of Symfony's underlying core. So far,
controller functions have been broken out into another file rather than in the
front matter. Exceptions have been brought over from Symfony as well.