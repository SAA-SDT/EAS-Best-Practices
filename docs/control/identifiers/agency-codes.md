---
layout: default
title: Agency codes
parent: Identifiers
nav_order: 3
---

# Agency codes

**Schema:** 
EAC-CPF 2.0

**Context:** 
Code or identifier for the institution or service responsible for the creation, maintenance, and/or dissemination of the EAS instance.

**Description:** 
Identify the institution or service responsible for the present EAS instance with a unique code or identifier, preferably according to the [International Standard Identifier for Libraries and Related Organizations (ISIL)](https://www.iso.org/standard/77849.html), ISO 15511:2019, within the element `<agencyCode>`. If this is not the case then Local institution codes may be given with the ISO 3166-1 alpha-2 country code as the prefix to aim for international uniqueness.

Use the attribute @status with the value "authorized" or "alternative" to declare whether the agency code is using an authorized value, e.g. a registered ISIL code, or an alternative one.

Use `<otherAgencyCode>` to record any alternative codes representing the agency.

**Example** 
```xml
<maintenanceAgency>
  <agencyCode status="authorized" vocabularySource="ISIL" vocabularySourceURI="http://id.loc.gov/vocabulary/identifiers/isil">US-ctybr</agencyCode>
  <agencyName>Beinecke Rare Book and Manuscript Library</agencyName>
  <otherAgencyCode status="authorized" valueURI="https://id.loc.gov/vocabulary/organizations/ctybr" vocabularySource="MARC Code List for Organizations" vocabularySourceURI="https://www.loc.gov/marc/organizations/">CtY-BR</otherAgencyCode>
  <otherAgencyCode status="alternative" valueURI="https://www.wikidata.org/wiki/Q814779" vocabularySource="Wikidata" vocabularySourceURI="https://www.wikidata.org/"> Q814779</otherAgencyCode>
</maintenanceAgency>
```
