---
layout: default
title: Alternative entity types
parent: Entity types
nav_order: 2
---

# Alternative entity types

**Schema:** 
EAC-CPF 2.0

**Context:** 
Encoding alternative types of agent being described in an EAC-CPF instance

**Description:** 
Next to `<entityType>`, EAC-CPF also includes the element `<otherEntityType>`. With `<otherEntityType>` it is possible e.g. to provide translations or specifications of the default values used in `<entityType>` or to include related agent types from other standards such as Records in Contexts (RiC). 
Similar to the plural and singular elements used in the `<description>` section (f.i. `<functions>` and `<function>` or `<occupations>` and `<occupation>`), `<otherEntityType>` is used within a wrapper element `<otherEntityTypes>` that also allows for a `<descriptiveNote>` to be included to add details with regard to the alternative entity types given. 

`<otherEntityType>` itself allows for the three vocabulary attributes (@valueURI, @vocabularySource, @vocabularySourceURI) and hence enables the connection to external vocabularies for the alternative agent type provided in `<otherEntityType><term>`. Same as all other singular elements, `<otherEntityType>` also comes with the optional sub-elements for date and place encoding, so that the alternative agent type can be bound to a specific timespan or location with regard to its use or applicability. This might e.g. be useful when a corporate body has changed its legal form over time and one would want to already emphasize this fact in the `<identity>` section, next to a potential use of `<legalStatus>` within the `<description>` section. 

**Examples**
```xml
<control>
    [...]
    <localTypeDeclaration id="termType" target="termTypeLocal">
        <reference>Types of terms</reference>
    </localTypeDeclaration>
    <localControl id="termTypeLocal">
        <term>translation</term>
        <term>specification</term>
        <term>relatedStandard</term>
    </localControl>
</control>
<cpfDescription>
    <identity>
        <entityType value="corporateBody"/>
        <nameEntry status="authorized" languageOfElement="de">
            <part>ICARus - Internationales Zentrum für Archivforschung</part>
        </nameEntry>
        <nameEntry status="authorized" languageOfElement="en-gb">
            <part>ICARus - International Centre for Archival Research</part>
        </nameEntry>
        <otherEntityTypes>
            <otherEntityType localType="translation" localTypeDeclarationReference="termType" 
            valueURI="https://d-nb.info/gnd/4128521-9" vocabularySource="GND">
                <term language Of Element="de">Körperschaft</term>
            </otherEntityType>
            <otherEntityType localType="specification" localTypeDeclarationReference="termType" 
            valueURI="https://d-nb.info/gnd/4043774-7" vocabularySource="GND">
                <term languageOfElement="de">Organisation</term>
            </otherEntityType>
            <otherEntityType localType="specification" localTypeDeclarationReference="termType" 
            valueURI="https://data.bnf.fr/ark:/12148/cb11951020r" vocabularySource="RAMEAU">
                <term languageOfElement="fr">Organisation</term>
            </otherEntityType>
            <otherEntityType localType="specification" localTypeDeclarationReference="termType" 
            valueURI="https://d-nb.info/gnd/4293729-2" vocabularySource="GND">
                <term languageOfElement="de">Nonprofit-Organisation</term>
            </otherEntityType>
            <otherEntityType localType="specification" localTypeDeclarationReference="termType" 
            valueURI="https://data.bnf.fr/ark:/12148/cb119498393" vocabularySource="RAMEAU">
                <term languageOfElement="fr">Associations sans but lucratif</term>
            </otherEntityType>
            <otherEntityType localType="specification" localTypeDeclarationReference="termType" 
            valueURI="https://d-nb.info/gnd/4062714-7" vocabularySource="GND">
                <term languageOfElement="de">Verein</term>
            </otherEntityType>
            <otherEntityType localType="specification" localTypeDeclarationReference="termType" 
            valueURI="https://data.bnf.fr/ark:/12148/cb13318322c" vocabularySource="RAMEAU">
                <term languageOfElement="fr">Associations</term>
            </otherEntityType>
        </otherEntityTypes>
    </identity>
</cpfDescription>
```
```xml
<control>
    [...]
    <localTypeDeclaration id="GNDO">
        <reference href="https://d-nb.info/standards/elementset/gnd">Gemeinsame Normdatei 
        Ontology</reference>
        <shortCode>GNDO</shortCode>
    </localTypeDeclaration>
   <localTypeDeclaration id="termType" target="termTypeLocal">
        <reference>Types of terms</reference>
    </localTypeDeclaration>
    <localControl id="termTypeLocal">
        <term>translation</term>
        <term>specification</term>
        <term>relatedStandard</term>
    </localControl>
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
       <otherEntityTypes>
           <otherEntityType 
           valueURI="https://d-nb.info/standards/elementset/gnd#RoyalOrMemberOfARoyalHouse" 
           vocabularySource="GNDO" 
           vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#"
           localType="specification" localTypeDeclarationReference="termType">
               <term languageOfElement="ger">Regierender Fürst oder Mitglied eines regierenden 
               Fürstenhauses</term>
            </otherEntityType>
        </otherEntityTypes>
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
        <otherEntityTypes>
            <otherEntityType languageOfElement="eng" 
            valueURI="https://www.ica.org/standards/RiC/ontology#Agent" vocabularySource="RiC-O" 
            vocabularySourceURI="https://www.ica.org/standards/RiC/ontology">
                <term>Agent</term>
            </otherEntityType>
            <otherEntityType languageOfElement="eng" 
            valueURI="https://www.ica.org/standards/RiC/RiC-O_v0-2.html#Group" 
            vocabularySource="RiC-O" 
            vocabularySourceURI="https://www.ica.org/standards/RiC/ontology">
                <term>Group</term>
            </otherEntityType>
            <otherEntityType languageOfElement="eng" 
            valueURI="https://www.ica.org/standards/RiC/RiC-O_v0-2.html#Family" 
            vocabularySource="RiC-O" 
            vocabularySourceURI="https://www.ica.org/standards/RiC/ontology">
                <term>Family</term>
            </otherEntityType>
        </otherEntityTypes>
    </identity>
</cpfDescription>
```
