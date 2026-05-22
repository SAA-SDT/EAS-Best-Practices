---
layout: default
title: Reparative Work
parent: Transparency in Descriptive Practices
nav_order: 4
---

# Reparative Work

**Scenario**: The EAS document and its description elements have been enhanced and undergone reparative work in all its descriptive elements.

It is to be noted that content warnings, e.g. “This collection contains historically offensive and harmful terminology of disabled people.” need to be documented following the content standard you are using for your descriptions like Describing Archives a Content Standard (DACS) and other national standards or an institutional policy. The content warnings display is furthermore dependent on the system you are using and how it is displaying the content warning.

**Recommendation**: In the control section of the EAS document, include a `<conventionDeclaration>` linking to the institution’s reparative policy, and a `<maintenanceEvent>` noting who conducted the review and enhancement when. In case, the reparative work has concentrated on certain elements only and not the whole EAS instance, references to the policy should be made from these elements specifically using their attribute conventionDeclarationReference and, where applicable, maintenanceEventReference.

```xml
<conventionDeclaration id="cdR1">
    <reference href="https://www.reparativeWorkPolicy/InformationPage>Reparative works policy</reference>
    <descriptiveNote>
        <p>Reparative work has been made to all of the descriptive parts of this EAS following the reparative work policy.</p>
    </descriptiveNote>
</conventionDeclaration>
```

```xml
<maintenanceEvent maintenanceEventType="updated" id=”rEvent1” target=”cdR1”>
    <agent agentType="human">
        <label>Jane Smith</label>
    </agent>
    <eventDateTime standardDateTime="2025-06-23T09:37:17.029-04:00"/>
    <eventDescription>This EAS description was reviewed and remediated following the reparative policy.</eventDescription>
</maintenanceEvent>
```
