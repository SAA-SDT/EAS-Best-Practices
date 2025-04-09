---
layout: default
title: audience
parent: EAS Value Lists
nav_order: 3
---

# audience

**Scope Note:**
To define the visibility of an element's content.

`@audience` is an attribute available in all elements of the EAS. Accepted values for `@udience` are listed below with scope notes.

___

## internal
**Example**
```xml
<otherIdentificationData audience="internal">Staff only notes about sensitive material</otherIdentificationData>
```

## external
**Example**
```xml
<ead audience="external">
```
Note: Even if the file at the root element is designated "external", elements within the record may be marked "internal".
