Speaker: Xavier Briand
# Symfony2 search engine propelled by Solr

Slides here: http://xavierbriand.github.com/training-solr

- Built on top of Lucene
- Companies include:
  - Etsy
  - AOL
  - etc
- Relatively simple to install

## Bridging Solr and Symfony

- link: http://solarium-project.org
- bundle: nelmioSolariumBundle

### Indexing

- "One index, one schema, n fields"
- src: ./config/schema.xml

``` xml
<fields>
	<field name="id" type="string" indexed="true" stored="true" required="true" />
	<!-- etc... -->
</fields>
```

- Get solarium, form query, store.
- Inject to Twig in "for" loop.

### Relevancy
- TF-IDF
- Coord
- lengthNorm

- Boost
  - Title > text

``` xml
	<field name="title" type="text_general" indexed="true" stored="true" />
```

### Faceting

- Means to organize results

### Highlight

### Spellchecker

### Autocomplete

Fuck it, just check out http://xavierbriand.github.com/training-solr/#/me
