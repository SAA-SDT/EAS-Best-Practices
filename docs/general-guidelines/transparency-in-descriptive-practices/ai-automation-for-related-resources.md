---
layout: default
title: AI Automation for Related Resources
parent: Transparency in Descriptive Practices
nav_order: 3
---

# Use of an AI Automation Tool to Enhance or Generate Related Resources

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
## Examples
- [Single digital object](#example-for-single-digital-object)
- [Single digital object with various forms](#example-for-single-digital-object-with-various-forms)
- [Single digital object consisting of several image files](#example-for-single-digital-object-with-various-forms)

### Example for single digital object

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

### Example for single digital object with various forms

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

### Example for single digital object consisting of several image files

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
