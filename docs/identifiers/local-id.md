---
layout: default
title: Local identifiers
parent: Identifiers
nav_order: 2
---

# Local identifiers

**Schema:** 
EAC-CPF

**Context:** 
Adding a local identifier in an attribute when naming related entities, resources, or functions.

**Description:** 
A local identifier for a related entity can be added to the optional attribute @valueURI, if the local identifier has its own URI. Otherwise use the optional attribute @localType, if the local identifier is a very local one and use @localTypeDeclarationReference to link to the according declaration of this @localType attribute.

**Examples**
```xml
<!-- In Control: Definition of the archival codes found in the Swedish National Archival Database, NAD -->
<localTypeDeclaration id="ltd2">  
	<reference href="https://sok.riksarkivet.se/nad">
    Swedish registry of archival reference codes in NAD
	</reference>
  <shortCode>Reference codes</shortCode>
  <descriptiveNote>  
    <p>The reference code for the archive used in NAD</p>
  </descriptiveNote>
</localTypeDeclaration>
```
```xml
<!-- Relation to the archive from the EAC-CPF entity being described -->
<relation>
  <targetEntity targetType="resource" valueURI="https://sok.riksarkivet.se/arkiv/9C96bDX9rH6cxG02H087k3">
    <part localTypeDeclarationReference="ltd2" localType="SE/ULA/11630">
      Uppsala domkapitel
    </part>
  </targetEntity>
  <relationType valueURI="https://www.ica.org/standards/RiC/ontology#isCreatorOf">
    Is creator of
  </relationType>
  <descriptiveNote>
    <p>Uppsala domkapitels arkiv var tidigare uppdelat i tre delar (1593–1900, 1901–1962, 1963–1999). 2017–2018 sammanfördes de äldsta två delarna till ett arkiv, Uppsala domkapitels arkiv I, varvid ett omfattande omordnings- och omförteckningsarbete företogs. Delen omfattande 1963–1999 kvarstår som ett eget arkiv under benämningen Uppsala domkapitels arkiv II.</p>
  </descriptiveNote>
</relation>
```
