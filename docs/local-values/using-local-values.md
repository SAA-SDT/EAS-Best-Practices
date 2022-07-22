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
When the local type declaration has been made it is possible in all elements where the local type attribute is available to reference the locally defined convention or value list. The step two of referencing is based upon the use of two attributes @localType and @localTypeDeclarationReference where the first gives the value or convention used and the second gives the reference to the local type declaration that has been used. The use of the @localTypeDeclarationReference assures that the local type declaration has been used by containing the identification of the declaration and it being checked through rules present in the schema by using xml:id and the identification reference mechanism.

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
