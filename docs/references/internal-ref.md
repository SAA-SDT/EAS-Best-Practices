---
layout: default
title: Internal references
parent: References
nav_order: 1
---

# Internal references

**Schema:**
EAC-CPF 2.0

**Context:** 
Creating a reference from one element to another element in a single EAC-CPF instance.

**Description:** 
It is possible to create internal references from one element to another element within a single EAC-CPF instance. For example, you may wish to reference a detailed `<place>` element from `<placename>` elsewhere in the EAC-CPF instance. The @id and @target attributes are used to create these internal references.

The @id attribute is available on all elements to assign an identifier to an element that is unique within the instance. The @target attribute is available on all elements, except `<eac>`, and can be used to refer to the @id of another element. To create the reference, use the @target attribute on the element you wish to create a reference from, and enter the value of the @id attribute on the element you wish to refer to, preceded by #. It is possible to refer to more than one element from a single element.

**Examples**
```xml
<occupation>
  <term>Assistant examiner - level III</term>
  <placeName target="#place1">Bern</placeName>
</occupation>
```
```xml
<place id="place1">
  <placeName>Bern</placeName>
  <placeRole>Place of work</placeRole>
  <address>
    <addressLine addressLineType="street">Stauffacherstrasse 65/59g</addressLine>
    <addressLine addressLineType="postalCode">3003</addressLine>
    <addressLine addressLineType="country">Switzerland</addressLine>
  </address>
</place>
```
