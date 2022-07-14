---
layout: default
title: Relation to a Resource
parent: Relations
nav_order: 2
---

# Relation to a Resource

<img src="https://github.com/SAA-SDT/EAS-Best-Practices/raw/main/images/relation-resource.png" width="450"/>

**Schema:**
EAC-CPF

**Context:**
Describe the relationship between the entity described and a resource, like archival records, fonds, papers, publications, images/photos etc.

**Description:**
Use the wrapper element `<relation>` to include all information about the related resource and the character of the relation. Use the required child element `<targetEntity>` to provide a title or name of the related resource. Use the optional child element `<relationType>` to specify the type of relation. Use the optional child element `<targetRole>` to specify the role of the related entity. Use `<date>`, `<dateRange>`, or `<dateSet>` for specifying the time period of the relationship and `<place>` for relevant location information. `<descriptiveNote>` may be included for more detailed specifications or explanations of the relationship.

If needed, use `<objectXMLWrap>` to embed XML documenting the related entity from any (or no) namespace.

**Examples**
```xml
<relation>
  <targetEntity targetType="resource">
    <part>Mémorial du colonel Gustafsson. - 1829</part>
  </targetEntity>
  <date>1829</date>
  <relationType valueURI="https://www.ica.org/standards/RiC/ontology#isCreatorOf" vocabularySource="RiC-O" vocabularySourceURI="https://www.ica.org/standards/RiC/ontology">is creator of</relationType>
  <targetRole>Publication</targetRole>
</relation>
```
