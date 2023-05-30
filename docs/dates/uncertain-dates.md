---
layout: default
title: Uncertain dates
parent: Dates
nav_order: 1
---

# Uncertain dates
**Schema:**
EAC-CPF 2.0

**Context:**
Encoding uncertain dates in `<date>`, `<toDate>`, `<fromDate>`

**Description:**
The attributes `@certainty`, `@notBefore` and `@notAfter` can be used with the `<date>`, `<toDate>`, `<fromDate>` elements to express the level of certainty of a particular date. `@notBefore` and `@notAfter` can be used to indicate the earliest and latest possible dates that an uncertain date might fall between. `@certainty` can be used to encode a term such as approximate, circa, or uncertain to indicate the level of certainty of the date provided. The `@calendar` and `@era` attributes are also available to provide additional information about a date.

EAC-CPF will also enable the use of the Extended Date/Time Format (EDTF), which has been included in the latest version of the ISO 8601 standard. This allows for the encoding of dates as ‘uncertain’ (?), ‘approximate’ (~), and ‘uncertain and approximate’ (%) within the machine-processable date in the `@standardDate` attribute for `<date>`, `<fromDate>` and `<toDate>`.

**Example**
```xml
<dateRange>
	<fromDate notBefore="1971" notAfter="1975">around 1973</fromdate>
	<toDate standardDate="1992">1992</toDate>
</dateRange>
```

```xml
<date certainty="uncertain" standardDate="1968?">c. 1968</date> 
```

```xml
<dateRange>
	<fromDate calendar="gregorian" certainty="approximate" era="ce" standardDate="1950">1950</fromDate>
	<toDate calendar="gregorian" certainty="approximate" era="ce" standardDate="2000">2000</toDate>
</dateRange>
```
