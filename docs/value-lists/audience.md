---
layout: default
title: audience
parent: Value lists
nav_order: 2
---

# audience
`@audience` may be used in all elements to define the content as "internal" or "external".

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
