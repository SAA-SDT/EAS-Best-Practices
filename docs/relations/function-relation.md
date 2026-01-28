---
layout: default
title: Relation to a function
parent: Relations
nav_order: 3
---

# Relation to a function

<img src="https://github.com/SAA-SDT/EAS-Best-Practices/raw/main/images/relation-function.png" width="350"/>

**Schema:**
EAC-CPF 2.0

**Context:**
Describe the relationship between the entity described and a function.

**Description:**
Use the wrapper element `<relation>` to include all information about the related function and the character of the relation. Use the required child element `<targetEntity>` to provide a name or title of the related function. Use the optional child element `<relationType>` to specify the type of relation. Use the optional child element `<targetRole>` to specify the role of the related entity. Use `<date>`, `<dateRange>`, or `<dateSet>` for specifying the time period of the relationship and `<place>` for relevant location information. `<descriptiveNote>` may be included for more detailed specifications or explanations of the relationship.

If needed, use `<objectXMLWrap>` to embed XML documenting the related entity from any (or no) namespace.
