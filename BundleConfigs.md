Speaker: Dennis Benkert -- @denderello https://twitter.com/denderello

Slides: http://de.slideshare.net/denderello/what-your-mother-didnt-tell-you-about-bundle-configurations-symfony-live-san-francisco-2012

# What your Mother never told you about Bundle configuration
- Focus on Validation


## Bad Configuration
Having a bad configuration is worse than bad code in terms of structure. Bad validation
suffers the same.

Example: "Redirect" has been mispelled in demo key. 301 redirects never made to 302 as defined.

Tools:
- Config Component
  - Locate
  - Load
  - Validate
  - Cache (*will not be covered)

## Locate & Load

Works with DIC:
``` php
use Symfony\Component\Config\FileLocator;
$locator = new Loader\XmlFileLoader(
	$container,
	new FileLocator('...') // Path for resources
);
```

Can be located like:

``` php
$loader->load('services.xml');
```

## Validate

Bundle Extension:
``` php
public function load($configs, /*...*/)
{
	$config = $this
		->processConfiguration(/*...*/);
	if (true === $config['enabled']){
		// do code here
	}
}
```

TODO: Get full code snippet above.

Config file:

``` yaml
your_bundle:
    enabled: true
```

YAML parses as valid PHP array for testing.

## Build a config tree

Treebuilder: validates your config files

Accepts types: `['Array', 'Boolean', 'Scalar']`

Tips:
- Use simple validation, not complex logic
- You can use custom errors
  - Provide a good error message if you override.

Arrays:
- Validation can include prototypes

## Using configuration
- Configure services vs using container in classes.
- Configuration needs structure
- Configuration needs conversion
- Configuration needs validation