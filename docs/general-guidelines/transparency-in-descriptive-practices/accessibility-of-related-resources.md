---
layout: default
title: Accessibility of Related Resources
parent: Transparency in Descriptive Practices
nav_order: 5
---

# Accessibility of Related Resources

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
## Examples
- [Single digital object with various forms](#example-of-single-digital-object-with-various-forms)
- [Single digital object consisting of several image files](#example-of-single-digital-object-with-various-forms)

### Example of single digital object with various forms

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

### Example of single digital object consisting of several image files
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
