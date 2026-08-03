---
layout: default
title: Encoding Unit Dates
parent: Dates
nav_order: 1
---

# Encoding Unit Dates

**Schema:** EAD 4.0

**Context:** Encoding dates of described materials within `<identificationData>`

**Description:**
Use `<unitDate>` and its sub-elements to encode dates when the described materials were created, issued, copyrighted, broadcast, etc. Where possible, follow agreed national or local conventions (such as the US [DACS standard](https://saa-ts-dacs.github.io/dacs/06_part_I/03_chapter_02/04_date.html)) for expressing dates consistently.

`<unitDate>` must contain one of the following sub-elements: `<date>`, `<dateRange>`, `<dateSet>` and `<textualDate>`. 

Use `<date>` to encode a single date in human- and machine-readable form. State the human-readable date as the content of the element. Provide a machine-readable date using the `@standardDate` attribute, formulated according to ISO 8601 or another rule.

For machine-readable uncertain or approximate dates, use [Extended Date/Time Format](https://www.loc.gov/standards/datetime/) (EDTF) in `@standardDate` or use `@notBefore` and `@notAfter` to capture the earliest and latest possible dates.

Use `<dateRange>` and its sub-elements `<fromDate>` and `<toDate>` to encode a range of dates in human- and machine-readable form. `<dateRange>` must contain either `<fromDate>` or `<toDate>`. Whenever possible, use both sub-elements: `<fromDate>` first, followed by `<toDate>`.

Use `<fromDate>` for the beginning of a date range and use `<toDate>` for the end of a date range. In both cases, state the human-readable date as the content of the element. Provide machine-readable dates using the `@standardDate` attribute, formulated according to ISO 8601 or another rule.

For machine-readable uncertain or approximate dates within `<fromDate>` and `<toDate>`, use `@standardDate` or `@notBefore` and `@notAfter` in the same manner as for `<date>`.

If the date range is open-ended (for instance, if there are frequent accruals of later materials), either omit `<toDate>` or use `<toDate>` with the @status attribute with the value "ongoing".

Use `<dateSet>` to encode more complex dates in human- and machine-readable form. Such dates consist of two or more distinct single dates or date ranges. Only use `<dateSet>` where it is appropriate to encode complex date information in this degree of granularity. 

`<dateSet>` requires at least two sub-elements: either two instances of `<date>`, two instances of `<dateRange>` or one instance of each. More than two can be used (in any combination) if required.

Use `<textualDate>` for free text statements of human-readable dates. These do not need to be expressed in a standardized or structured way. Date-specific attributes (`@dateChar`, `@calendar`, `@certainty`, `@era`, `@notAfter`, `@notBefore` or `@standardDate`) are not allowed within `<textualDate>`. 

When used as children of `<unitDate>`, `<date>`, `<dateRange>` and `<dateSet>` are not repeatable and cannot be used together. Choose one of them and use it once. However, `<date>` and `<dateRange>` are repeatable if used as children of `<dateSet>`.

- For a single date, use `<date>`
- For one discrete range of dates, use `<dateRange>`
- To use `<date>` and `<dateRange>` together or to repeat either element, nest them within `<dateSet>`

`<textualDate>` may be used as a child of `<unitDate>`, either alone or alongside `<date>`, `<dateRange>` or `<dateSet>`. `<textualDate>` is not allowed within `<dateSet>`. 

**Example:** 
A single date encoded using `<date>`
```
<identificationData>
  <unitDate>
    <date certainty="circa" standardDate="1973">circa 1973</date>
  </unitDate>
</identificationData>
```

**Example:** 
A date range encoded using `<dateRange>` alongside a free-text statement in `<textualDate>`
```
<identificationData>
  <unitDate>
    <dateRange>
        <fromDate standardDate="1988-11-01"/>  
        <toDate standardDate="2001-10-31"/>
    </dateRange>
    <textualDate>November 1988 through October 2001</textualDate>
  </unitDate>
</identificationData>
```

**Example:** 
A single date encoded using `<date>` alongside an alternative date format encoded using `<textualDate>`
```
<identificationData>
  <unitDate>
    <date standardDate="1617-11-03">1617 November 3</date>
    <textualDate>15 James 1, Morrow of All Souls</textualDate>
  </unitDate>
</identificationData>
```

**Example:** 
A complex date encoded using `<dateSet>` (with child elements `<dateRange>` and `<date>`) and `<textualDate>`
```
<identificationData>
  <unitDate>
    <dateSet>
      <date standardDate="1815~"></date>
      <dateRange>
        <fromDate standardDate="1819"></fromDate>
        <toDate standardDate="1825"></toDate>
      </dateRange>
      <date standardDate="1830"></date>
    </dateSet>
    <textualDate>approximately 1815, 1819-1825, 1830</textualDate>
  </unitDate>
</identificationData>
```