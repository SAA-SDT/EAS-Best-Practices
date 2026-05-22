---
layout: default
title: Transparency in Descriptive Practices Examples
parent: General guidelines
nav_order: 1
---

# Transparency in Descriptive Practices Examples
TS-EAS have created guidelines for when you are using the EAS Suite to document use of AI, reparative work and or accessibility both for the description itself and related resources. 

- [Use of an AI Automation Tool to Generate or Enhance Description](#example-1---use-of-an-ai-automation-tool-to-generate-or-enhance-description)
- [Use of an AI Automation Tool to Enhance or Generate Related Resources](#example-2---use-of-an-ai-automation-tool-to-enhance-or-generate-related-resources)
- [Reparative Work](#example-3---reparative-work)
- [Accessibility of EAS Document](#example-4---accessibility-of-eas-document)
- [Accessibility of Related Resources](#example-5---accessibility-of-related-resources)

**Schema:**
EAD, EAC-CPF, EAC-F

**Context:**
Below examples are shown on how different transparency is recommended to be stated using `<control>` and `<conventionDeclaration>` for documenting tools and policies and where in an EAS document the use is recorded.

**Description:**
To foster trust and promote accountability within our user community, it is critical to clearly document the decisions made by archives when creating, revising, or enhancing archival description. This includes explaining the methods used to describe collections, such as specifying which parts of the description process were generated or automated by artificial intelligence (AI), articulating how archivists’ decisions, perspectives, and biases might have shaped the description - and how such biases are being addressed in the context of reparative efforts, and noting any accessibility features or potential barriers to ensure a more inclusive digital world for all users. 

Currently, the Encoded Archival Standards (EAS) do not designate specific elements for capturing information related to transparency in descriptive practices at such detailed levels. Rather than introducing new elements to accommodate every future scenario, the recommendation is to leverage one or more of the existing `<conventionDeclaration>` elements in the control section of an EAS description. This element is the same across all of the EAS and is intended for recording the rules and conventions applied for compiling the descriptions. For versioning and attribution, use the existing `<maintenanceEvent>` element to record who made changes and when and to include a description of the change where applicable and useful. 

To be noted is that recording accessibility and use of AI will require extra efforts to be maintained and kept accurate. There might be a need for the creation of a policy describing how and when these statements are created. Such a policy should also, for example, cover how and when to do updates with new statements that are replacing the existing statements. There is also a necessity to determine if the statement is only pertaining to resources in the own repository and its collections. What is provided here is a recommendation on how to document it using the EAS standards. 

Below are various examples of how these different statements should be recorded in an EAS document. Note that in some cases the recommendations are aimed at a specific EAS standard and in other cases pertain to all the EAS.

## Example 1 - Use of an AI Automation Tool to Generate or Enhance Description

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

## Example 2 - Use of an AI Automation Tool to Enhance or Generate Related Resources

**Scenario**: The EAD finding aids describe related resources in the form of digital documents that have been generated and/or enhanced using the AI tools AICreator and AIEnhancer.

**Recommendation**: In the control section of the EAS document, add a `<conventionDeclaration>` for each tool. No `<maintenanceEvent>` is required unless the EAS description itself has been updated. There will be references to the tools from a specific resource where it is known that the related digital document has been created or enhanced by the tools.

```xml
<conventionDeclaration id="cdAI1">
    <reference href="https://www.AICreator/InformationPage”>AICreator</reference>
    <descriptiveNote>
        <p>The tool AICreator has been used to generate the related documents.</p>
    </descriptiveNote>
</conventionDeclaration>
<conventionDeclaration id="cdAI2">
    <reference href="https://www.AIEnhancer/InformationPage”>AIEnhancer</reference>
    <descriptiveNote>
        <p>The tool AIEnhancer has been used to enhance the related documents.</p>
    </descriptiveNote>
</conventionDeclaration>
```

**Example 2a - Single digital object**

```xml
<c level="item">
    <identificationData>
        <unitTitle>Plan of Piazza San Paolo, Hamrun showing the proposed shifting of an existing tramway pole.</unitTitle>
        <unitId>PDM-09-62719</unitId>
    </identificationData>
    <formsAvailable>
        <formAvailable formAvailableType="analogOriginal">
            <label>Plan of Piazza San Paolo</label>
            <physicalDescription>
                <physicalFacet>in colour</physicalFacet>
            </physicalDescription>
        </formAvailable>
        <formAvailable formAvailableType="digitalDerived" valueURI="https://arkivji.org.mt/share/Plans/PDM62719.jpg" conventionDeclarationReference=”cdAI2”>
            <label>PDM62719.jpg</label>
            <physicalDescription>
                <dimensions>
                    <quantity>1090 x 917</quantity>
                    <unitOfMeasurement>pixel</unitOfMeasurement>
                </dimensions>
            </physicalDescription>
            <descriptiveNote>
                <p>The tool AIEnhancer has been used to improve visibility and readability of some of the thinner lines of the plan and the writings along the sides of it.</p>
            </descriptiveNote>
        </formAvailable>
    </formsAvailable>
</c>
```

**Example 2b - Single digital object with various forms**

```xml
<c level="file">
    <identificationData>
        <unitTitle>Brief an Ludwig Rütimeyer / von Charles Darwin</unitTitle>
    </identificationData>
    <formsAvailable>
        <formAvailable valueURI="https://www.e-manuscripta.ch/titlepage/doi/10.7891/e-manuscripta-96018" coverage="part" conventionDeclarationReference=”cdAI1”>
            <label>Titelseite</label>
            <role>Thumbnail</role>
            <descriptiveNote>
                <p languageOfElement="ger">Titelseite zur Vorschauansicht; automatisch erstellt mit dem Tool AICreator</p>
                <p languageOfElement="eng">title page as preview; created automatically using the tool AICreator</p>
            </descriptiveNote>
        </formAvailable>
        <formAvailable valueURI="https://doi.org/10.7891/e-manuscripta-96018" coverage="whole">
            <label>Brief an Ludwig Rütimeyer / von Charles Darwin</label>
            <role>Onlineansicht</role>
        </formAvailable>
        <formAvailable valueURI="https://www.e-manuscripta.ch/bau/download/pdf/2809505" coverage="whole">
            <label>pdf/2809505</label>
            <role>Download</role>
        </formAvailable>
    </formsAvailable>
</c>
```

**Example 2c - Single digital object consisting of several image files**

```xml
<formsAvailable>
    <formAvailable valueURI="https://collections.library.yale.edu/catalog/2008313" coverage="whole" formAvailableType="digitalDerived"> 
        <label>The Pippa and Porthos</label>
        <formAvailableId conventionDeclarationReference="cdAI2" valueURI="https://collections.library.yale.edu/iiif/2/1044151/full/full/0/default.jpg">The Pippa and Porthos (cover)</formAvailableId>
        <formAvailableId valueURI="https://collections.library.yale.edu/iiif/2/1044153/full/full/0/default.jpg">The Pippa and Porthos (titlepage)</formAvailableId>
        <formAvailableId conventionDeclarationReference="cdAI2" valueURI="https://collections.library.yale.edu/iiif/2/1044154/full/full/0/default.jpg">The Pippa and Porthos (p. 1)</formAvailableId>
        [...]
        <descriptiveNote>
            <p>Digitized pages of Barrie’s "The Pippa and Porthos."</p>
             <p>The tool AIEnhancer has been used with the cover and some of the digitized pages to correct their color palette, which had been affected during digitization.</p>
         </descriptiveNote>
    </formAvailable>
</formsAvailable>
```

## Example 3 - Reparative Work

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

## Example 4 - Accessibility of EAS Document

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

## Example 5 - Accessibility of Related Resources

**Scenario**: The EAD finding aid documenting related resources in the form of digital documents that have been created and/or enhanced to comply with accessibility policies and standards.
To be noted is that accessibility in the form of a statement like “This collection contains 20-pound bound volumes. To access these materials, please request handling assistance.” or “This collection consists of paper records without digital surrogates. For accessibility requests, please contact us.” is recommended to be placed in the EAD element `<accessConditions>`.

**Recommendation**: In the control section of the EAS document, add a `<conventionDeclaration>` referencing the accessibility policy and/or standard. No `<maintenanceEvent>` is required unless the EAS description itself was changed. There will be references to the `<conventionDeclaration>` from a specific resource where it is known that the related digital document has been created or enhanced to comply with the accessibility policies and standards.

```xml
<conventionDeclaration id="cdA1">
    <reference href="https://www.accessibilityPolicy/InformationPage">Accessibility policy</reference>
    <descriptiveNote>
        <p>All related resources have undergone work either within its creation or during an updated project to make sure all the related resources follow the accessibility policy.</p>
    </descriptiveNote>
</conventionDeclaration>
```

**Example 5a - Single digital object with various forms**

```xml
<c level="file">
    <identificationData>
        <unitTitle>Brief an Ludwig Rütimeyer / von Charles Darwin</unitTitle>
    </identificationData>
    <formsAvailable>
    <formAvailable valueURI="https://www.e-manuscripta.ch/titlepage/doi/10.7891/e-manuscripta-96018" coverage="part">
        <label>Titelseite</label>
        <role>Thumbnail</role>
    </formAvailable>
    <formAvailable valueURI="https://doi.org/10.7891/e-manuscripta-96018" coverage="whole" conventionDeclarationReference=”cdA1”>
        <label>Brief an Ludwig Rütimeyer / von Charles Darwin</label>
        <role>Onlineansicht</role>
        <descriptiveNote>
            <p language of element="ger">Erweiterte Zoomfunktionen sowie eine Transkription des Briefs, die über ein Braillelesegerät zugänglich ist, wurden hinzugefügt, um die Zugänglichkeit für Nutzer*innen mit Sehschwächen und Sehschädigungen zu verbessern.</p>
            <p language of element="eng">Advanced zoom functionalities and a transcription of the letter, which can be accessed via braille reader, have been added to improve the accessibility for users with visual impairments.</p>
        </descriptiveNote>
    </formAvailable>
    <formAvailable valueURI="https://www.e-manuscripta.ch/bau/download/pdf/2809505" coverage="whole" conventionDeclarationReference=”cdA1”>
        <label>pdf/2809505</label>
        <role>Download</role>
        <descriptiveNote>
            <p language of element="ger">Eine Transkription des Briefs, die über ein Braillelesegerät zugänglich ist, wurde hinzugefügt, um die Zugänglichkeit für Nutzer*innen mit Sehschwächen und Sehschädigungen zu verbessern.</p>
            <p language of element="eng">A transcription of the letter has been added which can be accessed via braille reader to improve the accessibility for users with visual impairments.</p>
        </descriptiveNote>
        </formAvailable>
    </formsAvailable>
</c>
```

**Example 5b - Single digital object consisting of several image files**
```xml
<formsAvailable>
    <formAvailable valueURI="https://collections.library.yale.edu/catalog/2008313" coverage="whole" formAvailableType="digitalDerived">
        <label>The Pippa and Porthos</label>
        <formAvailableId valueURI="https://collections.library.yale.edu/iiif/2/1044151/full/full/0/default.jpg"> The Pippa and Porthos (cover)</formAvailableId>
        <formAvailableId valueURI="https://collections.library.yale.edu/iiif/2/1044153/full/full/0/default.jpg"> The Pippa and Porthos (titlepage)</formAvailableId>
        <formAvailableId conventionDeclarationReference="cdA1" valueURI="https://collections.library.yale.edu/iiif/2/1044154/full/full/0/default.jpg"> The Pippa and Porthos (p. 1)</formAvailableId>
        [...]
        <descriptiveNote>
            <p>Digitized pages of Barrie’s "The Pippa and Porthos."</p>
            <p>For those pages that contain text, a transcription which can be accessed via braille reader has been added to improve the accessibility for users with visual impairments.</p>
        </descriptiveNote>
    </formAvailable>
</formsAvailable>
```