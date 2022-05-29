---
layout: default
title: Single name
parent: Names
nav_order: 1
---

# Single name
### Schema
EAC-CFP
### Context
Encoding a single name, if necessary with multiple name parts.
### Description
Use a single `<nameEntry>` element within `<identity>` to enter a single name for an entity. Add attributes to define the names language, status, designation for display or other properties. 
Use the element `<part>` to distinguish between parts of a name, if necessary.
Use the element `<useDates>` to indicate the dates the name was used.
Use several elements `<nameEntry>` within <identity> when an entity used different names over time.

### Examples
[nameEntry](https://eac.staatsbibliothek-berlin.de/schema/taglibrary/cpfTagLibrary2021Draft_EN.html#elem-nameEntry)
{: .btn .btn-outline }
(the link will need to be updated)


```xml
<nameEntry languageOfElement="de" preferredForm="true" status="authorized">
  <part localType="surname">Arendt</part>
  <part localType="firstname">Hannah</part>
</nameEntry>
```

```xml
<nameEntry status="authorized">
  <part>Technical Subcommittee for Encoded Archival Standards</part>
  <useDates>
    <dateRange>
        <fromDate>2015</fromDate>
        <toDate status="ongoing"/>
    </dateRange>
  </useDates>
</nameEntry>
```

```xml
<nameEntry>
  <part>Noel family, Earls of Gainsborough</part>
</nameEntry>
```
