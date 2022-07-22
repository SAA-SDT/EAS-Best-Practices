---
layout: default
title: Default entity types
parent: Entity types
nav_order: 1
---

# Default entity types
**Schema:** 
EAC-CPF

**Context:** 
Encoding the type of agent being described in an EAC-CPF instance

**Description:** 
Following the chapter 5.1.1 Type of entity in the International Standard Archival Authority Record for Corporate Bodies, Persons, and Families (ISAAR-CPF), EAC-CPF includes the element `<entityType>` within the `<identity>` section to define whether the entity being described is an organization of some kind, a person, or a family. Meant to provide a standardized anchor supporting interoperability across variations of local applications of EAC-CPF, `<entityType>` itself cannot have text, but requires the attribute @value to be used with either “corporateBody”, or “person”, or “family”. These three types are designed to be mutually exclusive, so that `<entityType>` also cannot be repeated.  

**Examples**
```xml
<identity>
    <entityType value="corporateBody"/>
    <nameEntry status="authorized" languageOfElement="de">
        <part>ICARus - Internationales Zentrum für Archivforschung</part>
    </nameEntry>
    <nameEntry status="authorized" languageOfElement="en-gb">
        <part>ICARus - International Centre for Archival Research</part>
    </nameEntry>
</identity>
```
```xml
<control>
    [...]
    <localTypeDeclaration id="GNDO">
        <reference href="https://d-nb.info/standards/elementset/gnd">Gemeinsame Normdatei 
        Ontology</reference>
        <shortCode>GNDO</shortCode>
    </localTypeDeclaration>
</control>
<cpfDescription>
    <identity>
        <entityType value="person"/>
        <nameEntry status="authorized">
            <part localType="https://d-nb.info/standards/elementset/gnd#personalName" 
            localTypeDeclarationReference="GNDO">Gustaf IV Adolf</part>
            <part localType="https://d-nb.info/standards/elementset/gnd#nameAddition" 
            localTypeDeclarationReference="GNDO">Kung av Sverige</part>
        </nameEntry>
     </identity>
</cpfDescription>
```
```xml
<control>
    [...]
    <localTypeDeclaration id="MARC21_MainEntry_PersonalName">
        <reference href="https://www.loc.gov/marc/bibliographic/bd100.html">MARC 21 Bibliographic 
        Full 100 - Main Entry-Personal Name (NR)</reference>
        <shortCode>MARC 21</shortCode>
    </localTypeDeclaration>
</control>
<cpfDescription>
    <identity>
        <entityType value="family"/>		
        <nameEntry status="authorized">
            <part localType="100$a">Mozart</part>
            <part localType="100$c">Familie : 17.-19. Jh.</part>
        </nameEntry>
    </identity>
</cpfDescription>
```
