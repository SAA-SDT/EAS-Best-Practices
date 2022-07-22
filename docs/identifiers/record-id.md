---
layout: default
title: Record identifiers
parent: Identifiers
nav_order: 2
---

# Record identifiers

**Schema:** 
EAC-CPF

**Context:** 
Unique identifier for the present EAS instance as globally unique identifier or as local identifier, but also unique identifier(s) for multiple records representing the same entity or resource in different systems. 

Record identifiers are associated with a record, not with the corporate body, person or familie, i.e. the entity, c.f. [identity identifier](entity-id.md).

**Description:** The present EAS instance needs a unique identifier within `<recordId>`, a required, not repeatable and non-empty element in `<control>`. The institution assigning the identifier ensures uniqueness of the `<recordId>` value within the archival descriptions under its control. Depending on the records environment, it can be a locally unique identifier or a globally unique identifier.

Any alternative or additional record identifiers for the same EAS instance, local or authority file record may be recorded in `<otherRecordId>`. Any merged, translated and aggregated records and also former or obsolete records are alternative records. Also use `<otherRecordId>` to enter identifiers of different records in different systems for the same entity.

Use the attributes @valueURI, @vocabularySource and @vocabularySourceURI to link to the source of the other record identifier and to identify the source system, esp. when using an authority record. The attribute @localType can be used to identify the institution or service responsible for providing the associated record identifier, by name or identifier.

The URL for the EAC-CPF instance itself may be captured in `<representation>`.

**Examples**
```xml
<control maintenanceStatus="derived">
  	<recordId>ES-28079-PARES-AUT-140149</recordId>
	  [...]
  <!-- This is the identifier used for this authority record in the original system. -->
    <otherRecordId localType="PARES" localTypeDeclarationReference="lTD1">140149</otherRecordId>
</control>
```
```xml
<control maintenanceStatus="new" publicationStatus="inProcess">
    <recordId>DE-1981_EAC-CPF_C002</recordId>
	    [...]
<!-- This is the identifier used for this authority record in the original system. -->
    <otherRecordId localType="original" localTypeDeclarationReference="lTD1">AUBT-ISAAR-C-002</otherRecordId>
</control>
```
