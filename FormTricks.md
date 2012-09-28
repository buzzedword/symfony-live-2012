Speaker: Bernhard Schussek

# Symfony2 Form Tricks

Outline
- Intro
- Data formats
- Data mapping
- Events

Today's example:

```
Legend: New Employee

Form   Employee:
  - Text   name
  - Money   salary
  - DateTime   birthDate
     [Choice   day, Choice   month, Choice   year]
```

``` php
$factory = Forms::createFormFactor();
```

Forms Have Names

``` php
$builder = $factory->createNamedBuilder('employee');
```


## Data formats
- Model data
- View data

[text]
- string
- string

[number]
- float
- localized string

[date]
- [string, integer, array, DateTime]
- [string, array]

``` php
$builder->add('createdAt', 'date', array(
	'input' => 'array',
	'widget' => 'single_text'
));
```

CAVEAT: If you need custom data, you always have to think about data types

### Normalized formal

``` php
$builder->addEventListener(FormEvents::BIND,
	function (FromEvent $event) {
// INCOMPLETE
	})
```

#### Tip

- Whenever you create a custom type, decide:
  - Model format?
  - Normalized format?
  - View format?

## Data transformation

```
Form:
  - model data
  - normalized data
  - view data
```

- Symfony\Component\Form\DataTransformerInterface
  - bijective
  - transform($data)
  - reverseTransform($data)

Example: ChoiceOrTextType

```
Label: Team
Choice: Other:
Text: Type a team
```

[choiceortext]
- string
- string
- array

Use ValueToChoiceOrTextTransformer