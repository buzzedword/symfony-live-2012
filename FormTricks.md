Speaker: Bernhard Schussek

Slides: https://speakerdeck.com/u/bschussek/p/symfony-form-tricks

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

#### Tip
The normalized data should have as trimmed down text as possible (? refer to slide)

### Case 1: Existing Team Selected
### Case 2: New Team Created

Check the value of "Other", if set create new team. Else, existing team.

#### Tip
Data transformers should never change the information stored in a form

Example: MyDateType

[mydate]
- MyDateTime
- [string, integer, array, DateTime]
- DateTime
- [array, string]

### Data Mapping
Data mapping is the mapping between a form and its fields

- Symfony\Component\Form\DataaMapperInterface
  - bijective
  - mapFormsToData($data, array $forms)
  - mapDataToForms($forms, array $data)

Implementations
- In Symfony
  - PropertyPathMapper
- Ideas:
  - DomDocumentMapper
  - EAVMapper

Example: Terms and Conditions

``` php
$builder->add('terms', 'checkbox', array(
	'mapped' => false,
	'data' => true,
));
$form->get('terms')->setData(true);
// MISSED
```

### STOP
Sorry guys, he's going way too fast here. Gotta absorb it myself. Please refer to slides.