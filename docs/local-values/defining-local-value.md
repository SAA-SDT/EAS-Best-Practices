---
layout: default
title: Defining a local value list to be used in the encoding
parent: Locally defined value lists
nav_order: 1
---

# Defining a local value list to be used in the encoding

**Schema:** 
EAC-CPF

**Context:** 
Defining local conventions and value lists that are not present in an online vocabulary possible to enrich the descriptions. 

**Description:** 
When there are no possible on-line resources to link to for enriching the descriptions it is possible to use a locally defined convention or value list. You can use one or more locally defined conventions or value lists. The first step in making use of a local convention or value list is to declare the use of it in the encoding of the record in the `<control>` section of the description. The element is named `<localTypeDeclaration>` and with its help you can give a reference to it in combination with a possible short code or acronym that the convention or value list is known by and an descriptive note where the convention or value list can be described so the understanding of the used convention or value list is presented. The element itself is given an identification in the identification attribute in either the form of a short code or an identification code making it possible to reference the specific convention or value list used in the element throughout the whole description. The identification attribute helps to make sure that the used local type declaration is present in the description through validation functions found in the schema. It is worth noting that the identification attribute is of the type xml:id for making the validation possible and thus the rules for how identifications are created are enforced. The rules say that an Identification can not start with a number it needs to start with letters and may not contain spaces.

**Examples** 
```xml
<localTypeDeclaration id="GNDO">
  <reference href="https://dnb.info/standards/elementset/gnd_20191015">
    GNDO
  </reference>
  <descriptiveNote>
    <p>Gemeinsame Normdatei Ontologie</p>
    <p languageOfElement="eng">Integrated Authority File Ontology</p>
    <p>Version 2019-10-15</p>
  </descriptiveNote>
</localTypeDeclaration>
```
```xml
<localTypeDeclaration id="ltd1">  
  <reference href="http://nad.ra.se/static/termlistor/Kategorikoder.htm">
    Category codes
  </reference>
  <shortCode>Category codes</shortCode>
 	<descriptiveNote>  
    <p>Codes for categorizing different types of authority records through organizational form, operation, function, archival organization etcetera.
 		</p>
	  <p>The category codes used in Swedish NAD</p>
	  <p>To be used in element function</p>
  </descriptiveNote>
</localTypeDeclaration>
```
