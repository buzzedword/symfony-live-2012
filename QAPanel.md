Speakers: All

# Round table Q&A

## When do I use XML vs YAML vs PHP?
By default, SF2 uses YAML since it is the easiest to use. YAML doesn't have the same
configurability as XML for edge cases, else, no difference. XML was used initially
since xsl could validate config files.

## Best tips for configuration, performance?
- composer autoloader
- generate bootstrap
  - APC cache
  - Use APC for doctrine metadata

## What to use to cache in Symfony?
Doctrine Common cache is best.

## Composer updates, how to stabilize?
Don't forget to remove the star from the version number to lock it and prevent it from
incrementing.

## How do I know when to create a new bundle?
Less is more. Don't always build out more bundles just because.

## What the crap is jobeet?
That'd be an SF1 FAQ demo app. It proooobably won't be updated by core to SF2, call for
contributors to update and DOC it.

## Where is the next conference?
Next conference will not be in SF. It will be big.
- East coast needs some love, needs local support.