---
layout: default
title: Referencing external vocabularies, ontologies, etc.
parent: References
nav_order: 2
---

# Referencing external vocabularies, ontologies, etc.

**Schema:**
EAC-CPF

**Context:**
Creating references to external vocabularies and ontologies from an EAC-CPF instance.

**Description:** 
The @valueURI, @vocabularySource and @vocabularySourceURI attributes are available on a number of elements for referencing external vocabularies or ontologies that have been used to populate the element.

@vocabularySource is used to identify a vocabulary that is the source of the element's value. @vocabularySourceURI is used for documenting a URI identifying the vocabulary source for the element's value. @valueURI is used for documenting a URI identifying the resource to be used as the element's value.

The attributes can be used individually, or combined to provide details about the source of the contents of an element, when an external vocabulary is being used.

**Examples**
```xml
<place>
  <placeName valueURI="https://d-nb.info/gnd/4005728-8" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">Berlin</placeName>		
  <placeRole valueURI="https://d-nb.info/standards/elementset/gnd#placeOfBusiness" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Sitz</placeRole>
</place>
```
