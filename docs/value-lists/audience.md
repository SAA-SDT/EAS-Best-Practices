---
layout: default
title: audience
parent: Value lists
nav_order: 2
---

# audience

**Scope Note:**
To define the visibility of an element's content.

**EAC-CPF 2.0:**
`@audience` may be used in all elements to define the content as "internal" or "external".

**EAD4:**
`@audienceEncoding` is used in `<control>` with the following values: *EASList, otherAudienceEncoding.* When choosing *EASList*, `@audience` will be expected with the following values: *internal, external.* When choosing *otherAudienceEncoding* specify the source of the values you will be using with `@audience` in `<conventionDeclaration>`.

___

## internal
**Example**
```xml
<materialSpec audience="internal">Staff only notes about sensitive material</materialSpec>
```

## external
**Example**
```xml
<ead audience="external">
```
Note: Even if the file at the root element is designated "external", elements within the record may be marked "internal".
