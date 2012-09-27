Speaker: Hugo Hamon
## Leveraging the Serializer Component

How it works:
- Start as an object
  - Pass through as an array
  - Encode to types:
     - XML
     - JSON
     - etc...
- Deserialize, start as a type
  - Pass through as an array
  - Decode to an object

## Normalizer interface
{images}

- NormalizerInterface normalizes objects to arrays, scalars
- Denormalizer does the reverse.

## Encoder Interface

- EncoderInterface encodes data into the given format
- DecoderInterface decodes a string into PHP data

## Including in symfony

``` php
use Symfony\Component\Serializer\Serializer;
use Symfony\Component\Serializer\Normalizer\GerSetMethodNormalizer;
use Symfony\Component\Serializer\Encoder\JsonEncoder;
use Symfony\Component\SerializerEncoder\XmlEncoder;

// TODO: Incomplete code
```

## Using

``` php
$serializer
	->serialize($object, 'xml');
```

``` xml
<response>
	<id/>
	<customer/>
	<reference><...</reference>
	<arrival>...</arrival>
	<!-- ... -->
</response>
```

## Ignoring attributes

``` php
$ignore = array('id', 'customer');
// TODO: Code incomplete
```

## Unserialize a string
``` php
$xml = '<response>...</response>';
// Convert an XML string to an array
$data = $serializer->decode($xml, 'xml');

// Convert the array to an object
$class = 'ns'
// TODO: code incomplete
```

## Adding support for YAML
{image} (not even trying. wait for slides.)



## Too fast to type, take note:
_At this point, the slides are too intensive to take notes, please wait for the slides to be published._
- JMS Serializer Bundle
- Twig Helpers
- Customizing the XML root node
- Serializing an object to a single XML node

