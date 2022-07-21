---
layout: default
title: Relation to a CPF entity
parent: Relations
nav_order: 3
---

# Relation to a CPF entity

<img src="https://github.com/SAA-SDT/EAS-Best-Practices/raw/main/images/relation-cpf.png" width="350"/>

**Schema:**
EAC-CPF

**Context:**
Describe the relationship between the entity described and a person, family or corporate body.

**Description:**
Use the wrapper element `<relation>` to include all information about the related entity and the character of the relation. Use the required child element `<targetEntity>` to provide a name of the related entity. Use the optional child element `<relationType>` to specify the type of relation. Use the optional child element `<targetRole>` to specify the role of the related entity. Use `<date>`, `<dateRange>`, or `<dateSet>` for specifying the time period of the relationship and `<place>` for relevant location information. `<descriptiveNote>` may be included for more detailed specifications or explanations of the relationship.

If needed, use `<objectXMLWrap>` to embed XML documenting the related entity from any (or no) namespace. 

**Example:**
```xml
<relation>
  <targetEntity targetType="person" valueURI="https://d-nb.info/gnd/120636123" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">
    <part>Sophie</part>
    <part>Baden, Großherzogin</part>
  </targetEntity>
  <dateRange localTypeDeclarationReference="date1" localType="dateOfBirthAndDeath">
    <fromDate>1801</fromDate>
    <toDate>1865</toDate>
  </dateRange>
  <relationType valueURI="https://www.ica.org/standards/RiC/ontology#hasFamilyAssociationWith" vocabularySource="RiC-O" vocabularySourceURI="https://www.ica.org/standards/RiC/ontology">has family association with</relationType>
  <targetRole>daughter</targetRole>
</relation>
```
