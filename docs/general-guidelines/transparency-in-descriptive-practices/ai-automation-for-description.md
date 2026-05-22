---
layout: default
title: AI Automation for Description
parent: Transparency in Descriptive Practices
nav_order: 2
---

# Use of an AI Automation Tool to Generate or Enhance Description

**Scenario**: The EAS document was either generated or enhanced with the help of the AI automation tool AIEnhancerOfDescriptions.

**Recommendation**: In the control section of the EAS document, add a `<conventionDeclaration>` for the tool, along with a `<maintenanceEvent>` documenting the event of creation or enhancement of the EAS document. In case, the tool was only used with some elements and not the whole EAS instance, references to the tool should be made from these elements specifically using their attribute `@conventionDeclarationReference` and, where applicable, `@maintenanceEventReference`.

```xml
<conventionDeclaration id="cdAI1">
    <reference href="https://www.AIEnhancerOfDescriptions/InformationPage”>AIEnhancerOfDescriptions</reference>
    <descriptiveNote>
        <p>The tool AIEnhancerOfCreatorDescriptions was used to [generate] or [enhance] all or [parts] of the descriptive texts in this finding aid.</p>
    </descriptiveNote>
</conventionDeclaration>
```
```xml
<maintenanceEvent maintenanceEventType="updated" id=”AIevent1” target=”cdAI1”>
    <agent agentType="machine">
        <label>AIEnhancerofFindingAids</label>
    </agent>
    <eventDateTime standardDateTime="2025-06-19T09:37:17.029-04:00"/>
    <eventDescription>This EAS description was [generated] or [enhanced] with the AIEnhancerOfDescriptions tool.</eventDescription>
</maintenanceEvent>
```