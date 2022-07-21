---
layout: default
title: Referencing external sources
parent: References
nav_order: 3
---

# Referencing external sources

**Schema:** 
EAC-CPF
**Context:** 
Creating references to external sources from an EAC-CPF instance.

**Description:** 
To reference external sources for the contents of the EAC-CPF instance, encode the details of the external source in the `<control>` sections, using the `<reference>` element within `<source>`. `<reference>` is a required child element of `<conventionDeclaration>`, `<localTypeDeclaration>`, and `<rightsDeclaration>` for identifying any rules and conventions applied in the compilation of the description. It is also a required child element of `<source>`, used to identify any sources used in compiling the description. `<source>` may include multiple child `<reference>` elements.

`<reference>` is an optional child element of `<abstract>`, `<chronItem>`, `<chronItemSet>`, `<event>`, `<eventDescription>`, `<item>`, and `<p>` where it is used to reference any external resources that provide additional context to the contents of that element.

`<reference>` can include an @href attribute to point to a specific address for a remote resource. 

**Examples**  
```xml
<source>
  <reference href="https://catalog.archives.gov/search?q=*:*&f.oldScope=descriptions&f.level=series&f.locationIds=53023101">Barack Obama Presidential Library</reference>
</source>
```
```xml
<relation>
  <targetEntity targetType="corporateBody">
    <part>Democratic Party</part>
  </targetEntity>
  <descriptiveNote>
    <p>
      <reference href="https://en.wikipedia.org/wiki/Barack_Obama">See more</reference>
    </p>
  </descriptiveNote>
</relation>
```
