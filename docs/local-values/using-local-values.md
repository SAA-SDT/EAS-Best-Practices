---
layout: default
title: Using a local value list to be used in the encoding
parent: Locally defined value lists
nav_order: 2
---

# Using a local value list to be used in the encoding

**Schema:** 
EAC-CPF

**Context:** 
Referencing a locally defined convention or value lists in the encoding. 

**Description:** 

Once `<localTypeDeclaration>` has been defined, it can be used via the @localType and @localTypeDeclarationReference attributes.  Use @localType to provide the element's type (e.g. type of name or date, type of function), which should come from the convention/list defined in `<localTypeDeclaration>`.  Use @localTypeDeclarationReference to refer to the convention/list; the value should match the @id for the convention/list in `<localTypeDeclaration>`.


**Examples**
```xml
<nameEntry status="authorized">
  <part localType="https://d-nb.info/standards/elementset/gnd#personalName" localTypeDeclarationReference="GNDO">Arendt, Hannah</part>
  <part localType="https://dnb.info/standards/elementset/gnd#dateOfBirthAndDeath" localTypeDeclarationReference="GNDO">1906-1975</part>
</nameEntry>
```
```xml
<function localType="1" localTypeDeclarationReference="ltd1">
  <term>stateAuthority</term>
  <descriptiveNote>
	  <p>En textuell beskrivning av organisationens verksamhetssektor</p>
  </descriptiveNote>
</function>
```
