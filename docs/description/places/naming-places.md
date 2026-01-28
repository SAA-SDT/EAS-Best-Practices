---
layout: default
title: Naming places
parent: Places and geographic features
nav_order: 1
---

# Naming places

**Schema:** 
EAC-CPF 2.0

**Context:** 
Encoding the name of a place in relation to other aspects of the entity description

**Description:** 
When describing a CPF entity, the description of this entity’s functions, activities, roles, occupations, mandates, etc. can play a vital role. In addition to simply naming such aspects, it furthermore can be useful to add a place dimension to them, e.g. when a person described has pursued their profession in various contexts and at several locations over time. Using the attributes @valueURI, @vocabularySource, and/or @vocabularySourceURI allows linking names of geographic locations in the element <placeName> to external vocabularies and ontologies that might hold additional information such as name variations or geographic coordinates of the place. Similarly, one could use the attribute @target to point to the @id attribute of a <place> element within the same EAC-CPF instance where more details about the named location have been provided.

**Example**
```xml 
<cpfDescription>
    <identity>
        <entityType value="person"/>
        <nameEntry status="authorized" languageOfElement="eng">
            <part localType="firstname">Toni</part>
            <part localType="lastname">Morrison</part>
        </nameEntry>
        <nameEntry status="authorized" languageOfElement="eng">
            <part localType="birthname">Chloe Ardelia Wofford</part>
        </nameEntry>
    </identity>
    <description>
        <occupations>
            <!-- [...] -->
            <occupation valueURI="https://www.wikidata.org/wiki/Q1622272" 
            vocabularySource="Wikidata" vocabularySourceURI="https://www.wikidata.org">
                <term>University teacher</term>
                <placeName>Texas Southern University, Houston</placeName>
                <placeName>Howard University, Washington, D.C.</placeName>
                <placeName>State University of New York at Albany</placeName>
                <placeName>New Brunswick campus, Rutgers University, New Jersey</placeName>
                <placeName>Bard College, Annandale-on-Hudson</placeName>
                <placeName>Cornell University, Ithaca</placeName>
                <placeName>Princeton University, Princeton</placeName>
            </occupation>
            <!-- [...] -->
        </occupations>
    </description>
</cpfDescription>
```
