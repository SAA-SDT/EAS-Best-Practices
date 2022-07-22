
---
layout: default
title: Sources of evidence
parent: Control
nav_order: 2
---

# Sources of evidence

**Schema:** 
EAC-CPF

**Context:** 
Source of evidence used for the establishment of the description of the CPF entity in the EAC-CPF instance.

**Description:** 
Within the element <source> any source of evidence for any information within an EAC-CPF instance can be given. The element `<source>` is repeatable within its plural element `<sources>`.

Use the required child element `<reference>` to include a textual identification of the reference, like author and title of a publication or article etc. In the case of online sources, use @href with `<reference>` to provide a URI.

Use the optional child element `<citedRange>` to point to a specific location within a source, like page numbers.

Use the optional `<descriptiveNote>` for any additional notes about the source. 

Use the optional `<objectXMLWrap>` to embed XML documenting the source from any namespace.

Add the attribute @id in `<source>` in order to identify this particular element. Use the attribute @sourceReference in any of the the elements of the identity area, the description area, and the relations allows for linking back to this particular element `<source>` in the current EAC-CPF instance.

Information given in the elements `<source>` and `<maintenanceEvent>`, cf. [Maintenance agency, history and status](maintenance.md), lay the foundation to the description of an assertion to the EAC-CPF description. 

**Examples** 
