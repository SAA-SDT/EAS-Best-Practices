---
layout: default
title: Instantiations
parent: Description
nav_order: 4
---

# Instantiations

**Schema:** 
EAD 4.0 (for `<formsAvailable>` and `<formAvailable>`)

**Context:**
Encoding of individual instantiations of the described records, including digital representations, microfiches, analog copies, and similar formats.

**Description:**
The instantiation concept is based on the specification of the Records in Contexts entity _RiC‑E06 Instantiation_ (see RiC-CM 1.0, pp. 25-2, [RiC-AG, 6c](https://ica-egad.github.io/RiC-AG/faq--the_instantiation_entity.html)). As defined in RiC-CM, an instantiation represents a distinct physical or digital instance of a record, understood as the concrete existence or materialization of its content. This encapsulates the idea that a record resource - understood as an intellectual or informational entity - may exist in multiple material or digital forms, each with its own characteristics, carrier, and technical properties.

Describing an instantiation is therefore specifying how a record exists in the world: its medium, format, file type, encoding, or physical carrier, as well as any technical metadata needed to manage, preserve, or provide access to it. This separated description of the intellectual content (the Record Resource) and its concrete instantiations allow us to model complex archival realities, such as:

- multiple copies or versions of the same record,
- digitized surrogates of analog originals,
- born‑digital records with various derivative formats,
- preservation masters, access copies, and other technical variants.

In EAD 4.0, the intellectual description of an archival unit - whether expressed in `<archDesc>` or within a component `<c>` - comes with additional sibling elements that identify, contextualize, and describe the provenance, history, and relationships of the material. Information relating to each of the analog, digital or hybrid instantiations of the described material is documented separately within `<formsAvailable>`, using elements intended for recording characteristics of the carrier, format, or technical properties.

Use the element `<formAvailable>`, sub-element of `<formsAvailable>`, to name and describe individual instantiations of the described records within a `<c>` element, or of the fonds/collections within the `<archDesc>` element. Group multiple instantiations of records or fonds/collections using the plural element `<formsAvailable>`. 

Within `<formAvailable>`, a wide range of information can be provided about the analog, digital or hybrid object, such as [access conditions](https://docs.google.com/document/d/1KFemrv_xE9YrqiJl4uPudwspTApUCDDUNXgK6DUU_Dg/edit?tab=t.0) (`<accessConditions>`), history of ownership or custody (`<custodHist>`), [physical descriptions](https://docs.google.com/document/d/1KFemrv_xE9YrqiJl4uPudwspTApUCDDUNXgK6DUU_Dg/edit?tab=t.0) (`<physicalDescription>`), technical requirements(`<physicalOrTechnicalRequirements>`), [relations](https://docs.google.com/document/d/1KFemrv_xE9YrqiJl4uPudwspTApUCDDUNXgK6DUU_Dg/edit?tab=t.0) (`<relations>`), or separated material (`<separatedMaterial>`).

Use the attribute `@formAvailableType` within `<formAvailable>` to specify the type of form or instantiation being described. An [EAS value list](https://saa-sdt.github.io/EAS-Best-Practices/docs/control/value-lists) provides predefined terms for this attribute. Use “analogOriginal” for analog originals such as paper files, charters, maps, and similar materials. For analog reproductions - including microforms or paper copies - use “analogDerived.” The term “digitalOriginal” applies to born‑digital materials, whereas “digitalDerived” should be assigned to digitally derived instantiations, such as digitized versions of analog originals or derivatives of born‑digital and digitized materials. Examples include a PDF generated from an email, a thumbnail or display surrogate of a TIFF image, or OCR‑extracted text from a digitized paper file. If a controlled vocabulary or list of terms is used, identify it within the control area.

<img width="1280" height="720" alt="Image" src="https://github.com/SAA-SDT/EAS-Best-Practices/raw/main/images/599897030-ff726c82-04e5-4e33-848b-0293696ec763.png" />

The record (blue) with reference number I. HA Rep. 219, Nr. 165 has 4 derived instantiations (yellow). One instantiation is called _Original_ and is the analog original record. Another instantiation is called _Mikrofilm_ with reference number _236/14_ and an analog form derived from the analog instantiation Original. A third instantiation is called _Master_ and has a TIFF file format. It is a digital instantiation, derived from the analog instantiation _Original_. The fourth instantiation is called _Derivat_ and has a JPG file format. It is a digital instantiation, derived from the digital instantiation _Master_. 

Blue lines indicate the relationship between the record and its instantiations, while yellow lines represent the relationships between the individual instantiations.

**Example:**
The example encodes the information illustrated in the image and described in the paragraphs below. 

```
<control audience="external" audienceEncoding="EASList" countryEncoding="iso3166-2" dateEncoding="iso8601" formAvailableTypeEncoding="EASList" languageEncoding="iso639-1" maintenanceStatus="revised" maintenanceStatusEncoding="EASList">
[...]
    <localTypeDeclaration id="archDesc">
        <reference href="https://deutsche-digitale-bibliothek.atlassian.net/wiki/spaces/DFD/pages/48105662/type"/>
        <shortCode>EAD(DDB)</shortCode>
    </localTypeDeclaration>
    <localTypeDeclaration id="unitId">
        <reference/>
        <shortCode>apeEAD</shortCode>
    </localTypeDeclaration>
</control>
[...]
<c level="file" id="Vz_6422c41f-6644-4bfd-bf5d-d84f6299552e">
    <identificationData>
        <unitId localType="call_number" localTypeDeclarationReference="unitId">I. HA Rep. 219, Nr. 165</unitId>
        <unitId localType="former_call_number" localTypeDeclarationReference="unitId">Pol.-Präs. Berlin Abt. I A</unitId>
        <unitDate>
            <dateRange>
                <fromDate standardDate="1920-01-01">1920</fromDate>
                <toDate standardDate="1923-12-31">1923</toDate>
            </dateRange>
        </unitDate>
        <unitTitle>Verordnungen des Reichspräsidenten zur Aufrechterhaltung der öffentlichen Ordnung</unitTitle>
        <genreForm>Akte/Amtsbuch</genreForm>
    </identificationData>
        <formsAvailable>
            <formAvailable formAvailableType="analogOriginal" audience="internal">
                <label>Original</label>
                <physicalDescription>
                    <extent>
                        <quantity>357</quantity>
                        <unitOfMeasurement>Blatt</unitOfMeasurement>
                    </extent>
                </physicalDescription>
            </formAvailable>
            <formAvailable formAvailableType="analogDerived" audience="external">
                <label>Mikrofilm</label>
                <formAvailableId>236/13</formAvailableId>
                <formAvailableId>236/14</formAvailableId>
                    <role>Benutzungsmedium (analog)</role>
                </formAvailable>
                <formAvailable formAvailableType="digitalDerived" audience="external" valueURI="https://archive.spk-berlin.de/actaproweb/document/Vz_39164428-8560-4b12-8fab-9a46604fb6f2">
                    <label>Derivat</label>
                    <role>Benutzungsmedium (digital)</role>
                    <physicalDescription>
                        <physicalFacet>JPG</physicalFacet>
                    </physicalDescription>
                </formAvailable>
            </formsAvailable>
            <accessConditions>
                <abstract>Vorlage nur als Mikrofilm/Mikrofiche/Digitalisat</abstract>
                <dateRange>
                    <fromDate/>
                    <toDate standardDate="2099-12-31">31.12.2099</toDate>
                </dateRange>
                    <p>Bestand ist vollständig digitalisiert.</p>
            </accessConditions>
</c>
```