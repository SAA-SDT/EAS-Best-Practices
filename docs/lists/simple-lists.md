---
layout: default
title: Simple lists for structuring
parent: Lists as part of narrative description
nav_order: 1
---

# Simple lists for structuring

**Schema:** 
EAC-CPF

**Context:** 
Using simple lists in the context of narrative description to structure information

**Description:** 
Elements such as `<biogHist>`, `<structureOrGenealogy>`, and `<generalContext>` can hold more narrative description relating to the history and general context of the EAC-CPF entity being described, respectively relating to the administrative structure of a corporate body or the genealogy of a family. Next to simple paragraphs (`<p>`) and - in the context of `<biogHist>` - the more specific chronological lists (`<chronList>`), which allow for capturing important dates and events in the life of an EAC-CPF entity, this also includes the option of creating lists (`<list>`). These can be useful when encoding enumerations, e.g. a list of different stages in the career of a person or a list of different departments and teams within an organization. Each stage is then represented by an `<item>` within the `<list>`. The optional element `<head>` can be used to include a title for the list, while the attribute @listType can be used to define whether the list would be “ordered”, i.e. numbered, or “unordered”, i.e. using symbols like bullets (●), squares (◼), or hyphens (-) for each list entry.

**Examples**
```xml
<cpfDescription>
        <identity>
            <entityType value="person"/>
            <nameEntry>
                <part localType="firstname">Joan Ruth</part>
                <part localType="birthname">Bader</part>
                <part localType="lastname">Ginsburg</part>
            </nameEntry>
        </identity>
        <description>
            <!-- [...] -->
            <biogHist>
                <!-- [...] -->
                <list listType="unordered">
                    <head>Legal and academic career</head>
                    <item>Clerkship for Judge Edmund L. Palmieri, U.S. District Court for the Southern District 
                    of New York</item>
                    <item>Research associate and associate director of the Columbia Law School Project on 
                    International Procedure</item>
                    <item>Professor at Rutgers Law School</item>
                    <item>Co-founder of the Women's Rights Law Reporter</item>
                    <item>Professor at Columbia Law School</item>
                    <item>Fellow of the Center for Advanced Study in the Behavioral Sciences at Stanford 
                    University</item>
                    <item>Co-founder of the Women's Rights Project at the American Civil Liberties 
                    Union</item>
                    <item>Judge on the District of Columbia Circuit of the U.S. Court of Appeals</item>
                    <item>Judge on the U.S. Supreme Court</item>
                </list>
            </biogHist>
        </description>
</cpfDescription>
```
```xml
<cpfDescription>
        <identity>
            <entityType value="corporateBody"/>
            <nameEntry>
                <part>United Nations</part>
            </nameEntry>
        </identity>
        <description>
            <!-- [...] -->
            <structureOrGenealogy>
                <!-- [...] -->
                <list listType="unordered">
                    <head>Principal organs</head>
                    <item>The General Assembly</item>
                    <item>The Security Council</item>
                    <item>The Secretariat with th Secretary-General</item>
                    <item>The Economic and Social Council</item>
                    <item>The International Council of Justice</item>
                    <item>The Trusteeship Council</item>
                </list>
            </structureOrGenealogy>
        </description>
</cpfDescription>
```
