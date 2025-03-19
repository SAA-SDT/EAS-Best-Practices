---
layout: default
title: Encoding unit dates
parent: Dates
nav_order: 1
---

# Encoding unit dates
**Schema:**
EAD 4.0

**Context:**
Encoding dates in `<identificationData>`

**Description:**
The sub-elements `<date>`, `<dateRange>` or `<dateSet>` with a new, fourth element `<textualDate>` can be used within `<unitDate>`. One of these four sub-elements is required, if `<unitDate>` is used. `<textualDate>` can be used to provide a natural language expression of the date. `<textualDate>` does NOT include date attributes: `@dateChar`, `@calendar`, `@certainty`, `@era`, `@notAfter`, `@notBefore`, `@standardDate`. If any of these are intended to be included, `<date>` should be used instead. 

**Example**
```xml
<identificationData>
	<textualDate>November 1988 through October 2001</textualDate>
	<dateRange>
    <toDate standardDate="1988-11"></toDate>
    <fromDate standardDate="2001-10"></fromDate>
  </dateRange>
</identificationData>
```
```xml
<identificationData>
	<textualDate>around 1973</textualDate>
	<date certainty="approximate" standardDate="1973"></date>
</identificationData>
```
