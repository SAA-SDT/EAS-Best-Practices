---
layout: default
title: Unknown or ongoing date ranges
parent: Dates
nav_order: 2
---

# Unknown or ongoing date ranges
**Schema:**
EAC-CPF

**Context:**
Encoding unknown or ongoing dates. 

**Description:**
In some circumstances it may not be possible to include information about particular dates in an EAC-CPF instance because they are either unknown, or because a date range is ongoing. An example of an ongoing date range is a Corporate Body that continues to operate. Standalone dates may be unknown or a date range may be incomplete, for example when a date of birth is unknown. It may be important to indicate the status of these dates, rather than omitting them from the EAC-CPF instance. 

The `@status` attribute can be used with the `<date>`, `<fromDate>` and `<toDate>` elements, with a controlled list of values, to allow for indicating where dates - or parts of a date range - may be unknown, or where a date range is ongoing. 

The available value for `<date>` and `<fromDate>` is "unknown", and the available values for `<toDate>` are "unknown" or "ongoing"

**Example**
```xml
<dateRange>
    <fromDate status="unknown"/>
	<toDate certainty="uncertain" standardDate="2010?">circa 2010</toDate> 
</dateRange>
```

```xml
<dateSet>
	<date standardDate="2014-07">July 2014</date>
	<dateRange>
		<fromDate standardDate="2016-09">September 2016</fromDate>
 		<toDate status="ongoing"/>
	</dateRange>
</dateSet>
```

```xml
<date status="unknown"/>
```
