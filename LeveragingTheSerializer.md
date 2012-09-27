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