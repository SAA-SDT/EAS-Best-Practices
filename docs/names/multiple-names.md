---
layout: default
title: Multiple names
parent: Names
nav_order: 2
---

# Multiple names
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Different forms of the same name
**Schema:**
EAC-CPF 2.0

**Context:**
Encoding multiple names for different forms of the same name.

**Description:**
Bundle multiple elements `<nameEntry>` within an element `<nameEntrySet>` within `<identity>` to enter different forms of the same name, e.g. official and alternative forms of a name, translations, transliterations, abbreviations, colloquial names etc.

Add attributes in `<nameEntry>`  to define the names language, status, designation for display or other properties. 

Use the element `<useDates>` within the element `<nameEntrySet>` to indicate the dates all names were used and use the same element with `<nameEntry>` to indicate the date one of the names was used.

**Example**
```xml
<nameEntrySet>
  <nameEntry status="authorized">
    <part localType="surname">Custer</part>
    <part localType="firstname">Mark</part>
  </nameEntry>
  <nameEntry status="alternative">
    <part localType="GitHubName">fordmadox</part>
    <useDates>
      <dateRange>
        <fromDate>2011</fromDate>
        <toDate status="ongoing"/>
      </dateRange>
    </useDates>
  </nameEntry>
</nameEntrySet>
```
---
## Qualify authorized and alternative names
**Schema:**
EAC-CPF 2.0

**Context:**
Qualify a name entry as authorized or alternative name of an entity according to ISAAR(CPF) 5.1.2.

**Description:**
Use the attribute @status for the element `<nameEntry>` and select one of the given values "authorized" or "alternative" to indicate if a name is authorized or alternative. 

**Example**
```xml
<nameEntrySet>
  <nameEntry status="authorized">
    <part localType="surname">Custer</part>
    <part localType="firstname">Mark</part>
  </nameEntry>
  <nameEntry status="alternative">
    <part localType="GitHubName">fordmadox</part>
  </nameEntry>
</nameEntrySet>
```
---
## Reflect parallel usage according to cataloging rules in North America
**Schema:**
EAC-CPF 2.0

**Context:**
Qualify a set of name entries as parallel names according to cataloguing rules in North America.

**Description:**
Use the attribute `@localType` with the value “parallel” within `<nameEntrySet>` to reflect the usage of parallel names in North America. 

Use the attribute `@localType` in `<nameEntry>` to specify the type of parallel name used, e.g. former, translation, abbreviation etc.

**Example**
```xml
<nameEntrySet localType="parallel">
  <nameEntry languageOfElement="de" preferredForm="true" status="authorized" localType="native">
    <part localType="surname">Arendt</part>
    <part localType="firstname">Hannah</part>
  </nameEntry>
  <nameEntry languageOfElement="ja" scriptOfElement="Jpan" preferredForm="false" status="authorized" localType="translation">
    <part localType="surname">アーレント</part>
    <part localType="firstname">ハナ</part>
  </nameEntry>
  <nameEntry languageOfElement="en" preferredForm="false" status="authorized">
    <part localType="surname">Arendt</part>
    <part localType="firstname">Hannah</part>
  </nameEntry>
</nameEntrySet>
```
---
## Qualify a name as preferred name for display purposes
**Schema:**
EAC-CPF 2.0

**Context:**
Qualify a name entry as preferred name for display purposes.

**Description:**
An entity with multiple names needs one name as preferred name for display purposes. If there are multiple equal names over time, i.e. multiple `<nameEntry>` elements as siblings and child elements of `<identity>`, multiple preferred names are possible. If there are multiple forms of a name, i.e. multiple `<nameEntry>` elements within `<nameEntrySet>`, only one of the names should be declared as the preferred name for display purposes.

**Example**
```xml
<nameEntrySet localType="parallel">
  <nameEntry languageOfElement="de" preferredForm="true" status="authorized" localType="native">
    <part localType="surname">Arendt</part>
    <part localType="firstname">Hannah</part>
  </nameEntry>
  <nameEntry languageOfElement="ja" scriptOfElement="Jpan" preferredForm="false" status="authorized" localType="translation">
    <part localType="surname">アーレント</part>
    <part localType="firstname">ハナ</part>
  </nameEntry>
  <nameEntry languageOfElement="en" preferredForm="false" status="authorized">
    <part localType="surname">Arendt</part>
    <part localType="firstname">Hannah</part>
  </nameEntry>
</nameEntrySet>
```
