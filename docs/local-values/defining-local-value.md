---
layout: default
title: Defining a local value list to be used in the encoding
parent: Locally defined value lists
nav_order: 1
---

# Defining a local value list to be used in the encoding

**Schema:** 
EAC-CPF 2.0

**Context:** 
Defining local conventions and value lists that are not present in an online vocabulary possible to enrich the descriptions. 

**Description:** 
When there are no appropriate type attributes to fully describe an element, it is possible to use one or more locally defined conventions or value lists.  First, declare the type convention/list in the `<localTypeDeclaration>` element within the `<control>` section.  Use the @id attribute to "name" the convention/list (which will be referred to via @localTypeDeclarationReference in the EAC instance).  Note that @id uses the `xml:id` data type, and thus cannot start with a number and cannot include spaces.

Use the required `<reference>` element to identify the convention or value list via a human-readable label, and the @href attribute to provide a URI for the source, if available.  Use @descriptiveNote to provide further information about the convention/list, such as a brief description or the version used by the EAC instance.

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
