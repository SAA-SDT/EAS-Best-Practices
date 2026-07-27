---
layout: default
title: Access and Use
parent: Description
nav_order: 1
---

# Access and Use

**Schema:**
EAD 4.0 (for `<accessConditions>` and `<useConditions>`).

**Context:**
Encoding information about availability conditions or usage rights of the described materials within `<archDesc>`, `<c>` or its numbered counterparts, or within `<formAvailable>`.

For defining licenses and copyright information within the description itself, see [Rights Declaration](/EAS-Best-Practices/docs/control/rights.html).

**Description for `<accessConditions>`:**

Information about conditions or restrictions affecting the availability of archival material belongs in `<accessConditions>`. Avoid confusing or conflating the content of this element with `<useConditions>`.

The kinds of information to be mentioned in `<accessConditions>` include:

- Archive material being closed to public access for privacy-related or other legal reasons
- Access restrictions required by donors or depositors
- Access restrictions due to the physical condition of the material
- Requirements to make an appointment, request special permission for access, or view material under close supervision
- Archival material being available without restriction

Follow national or local conventions when populating this element.

If the access conditions relate to a specific instantiation of a record that has been described within the EAD instance or finding aid, use `<accessConditions>` as a child element of `<formAvailable>`. Otherwise, use `<accessConditions>` as a child element of `<archDesc>`, `<c>` or its numbered equivalents, at whichever level is appropriate.

Use `<dateRange>` to provide information about the time span during when the specified access conditions apply. This is optional but highly recommended if the date when restrictions will end is known.

The other child elements available within `<accessConditions>` are `<abstract>` (for a brief summary of the relevant information), and `<p>` and `<formattingExtension>` for longer text. If more than one of these is used, the prescribed order is: `<abstract>`, `<dateRange>`, `<formattingExtension>` or `<p>`.

**Description for `<useConditions>`:**

Information about usage rights for archival material after access has been granted belongs in `<useConditions>`. Avoid confusing or conflating the content of this element with `<accessConditions>`.

The kinds of information to be mentioned in `<useConditions>` include:

- Use or reuse being limited for legal reasons, such as copyright or other intellectual property rights
- Use or reuse restrictions required by donors or depositors
- Copying restrictions due to the physical condition of the material
- Requirements to request special permission for copying, transcription or publishing
- Requirements for specific acknowledgements when reusing the material for display or publication
- Archival material being available for use or reuse without such conditions or restrictions

Follow national or local conventions when populating this element.

If the use conditions relate to a specific instantiation of a record that has been described within the EAD instance or finding aid, use `<useConditions>` as a child element of `<formAvailable>`. Otherwise, use `<useConditions>` as a child element of `<archDesc>`, `<c>` or its numbered equivalents, at whichever level is appropriate.

Use `<dateRange>` to provide information about the time span during when the specified use conditions apply. This is optional but highly recommended if the date when restrictions will end is known.

The other child elements available within `<useConditions>` are `<abstract>` (for a brief summary of the relevant information), and `<p>` and `<formattingExtension>` for longer text. If more than one of these is used, the prescribed order is: `<abstract>`, `<dateRange>`, `<formattingExtension>` or `<p>`.

**Example**
An access condition that applies to a specific instantiation of a record:  
```
<formAvailable>
  <accessConditions>
    <abstract>Unavailable due to mold damage. Use digital surrogate. </abstract>
    <p>Access to this document is not possible without prior conservation treatment because it has been identified as mold damaged. If possible, use the digital copy.</p>
  <formAvailable>
```

**Example**
An access condition that applies during a specified time period: 
```
<c>
  <accessConditions>
    <abstract>Closed to public access.</abstract> 
    <dateRange>
      <fromDate standardDate="2022-06-01">2022 June</fromDate>
      <toDate standardDate="2035-02-14">2035 February 14</toDate>
    </dateRange> 
    <p>Personal letters received by Jenkinson are closed to public access until 15 years after his death, as requested by the donor in June 2022. They will become available from 14 February 2035.</p>
  </accessConditions>
</c>
```

**Example**
A use condition containing information about copyright and permissions for reuse:
```
<c>
  <useConditions>
    <abstract>Copyright owner's permission required.</abstract>
    <dateRange>
      <toDate standardDate="2039-12-31">2039</toDate>
    </dateRange> 
    <p>Unpublished manuscripts remain in copyright until 2039. Permission from the copyright holder (the author's granddaughter) is required for reproduction or extensive quotation. It is the user's responsibility to obtain such permission. Please contact staff to request contact details for the copyright holder.</p>
    <p>Where permission is granted for use in published works, the acknowledgement to use is: 'Copyright material is reproduced by permission of the Jenkinson family.'</p>
  </useConditions>
</c>
```