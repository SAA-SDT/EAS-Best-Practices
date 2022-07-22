---
layout: default
title: Entity and identity identifiers
parent: Identifiers
nav_order: 4
---

# Entity and identity identifiers

**Schema:** 
EAC-CPF

**Context:** 
Identifier associated with the corporate body, person or family, i.e. the entity, being described in the EAC-CPF instance.

**Description:** 
The repeatable element `<identityId>` records identifiers such as legal identifiers, typically assigned by an authoritative agency. These identifiers can be (non exhaustive listing): business numbers, CAGE codes, Tax Identification numbers, personal registration numbers, passport numbers, ORCID ID, ISNI etc.

**Examples**
```xml
<identityId localType="RegistrationCode">222000-3103</identityId>
```
```xml
<identityId localType="VATRegistrationCode”>SE222000310301</identityId>
```
```xml
<identityId localType="EInvoiceID">2220003103</identityId>
```
