---
layout: default
title: Accessibility of EAS Document
parent: Transparency in Descriptive Practices
nav_order: 5
---

# Accessibility of EAS Document

**Scenario**: The EAS document and its description elements have been enhanced with addition of markers to support accessibility of the document when viewed using a transformation for a system with these capabilities.

**Recommendation**: In the control section of the EAS document, include a `<conventionDeclaration>` referencing the accessibility policy, and a `<maintenanceEvent>` describing the event of creation or enhancement of the EAS document. In case, the tool was only used with some elements and not the whole EAS instance, references to the tool should be made from these elements specifically using their attribute `@conventionDeclarationReference` and, where applicable, `@maintenanceEventReference`.

```xml
<conventionDeclaration id="cdA1">
    <reference href="https://www.accessibilityPolicy/InformationPage">Accessibility policy</reference>
    <descriptiveNote>
        <p>Throughout this EAS document work has been carried out to enhance the accessibility when viewing this document using the Accessibility tool within this institution.</p>
    </descriptiveNote>
</conventionDeclaration>
```
```xml
<maintenanceEvent maintenanceEventType="updated" id=”rEvent1” target=”cdR1”>
    <agent agentType="human">
        <label>Jane Smith</label>
    </agent>
    <eventDateTime standardDateTime="2025-06-23T09:37:17.029-04:00"/>
    <eventDescription>This EAS description was reviewed and enhanced following the accessibility policy.</eventDescription>
</maintenanceEvent>
```