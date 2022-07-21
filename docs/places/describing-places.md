---
layout: default
title: Describing places
parent: Places and geographic features
nav_order: 2
---

# Describing places

**Schema:**
EAC-CPF

**Context:** 
Encoding the name of a place of relevance to the entity being described along with further details about the place

**Description:** 
Places tell a CPF entity’s story, might it be their place of birth or death, a place where they lived or worked, a place where an organization was established and made an impact. Places also provide anchor points linking one entity to another via the locations where their paths crossed. EAC-CPF enables a more detailed description of such places of relevance in the `<places><place>` element within its `<description>` section as well as in the context of a chronological list, e.g. for building a biography, and in the context of describing relationships between the entity being described and other entities. Next to naming a place using the element `<placeName>`, describing a place also can include specification of the place’s role (`<placeRole>`), address or contact details for a place (`<address><addressLine>` and `<contact><contactLine>` respectively) and geographic coordinates for a place (`<geographicCoordinates>`). At least one of these aspects has to be covered when describing a place. In addition, an optional date dimension can be added to places of relevance and more descriptive information can be added when describing places. 

When describing several places of relevance for the described entity, it is recommended to repeat the complete `<place>` element and to make use of sub-elements such as `<placeRole>`, `<address>`, `<contact>` or `<geographicCoordinates>` in order to distinguish between the different places. For encoding variations of the name of a place, on the other hand, it is recommended to repeat only the `<placeName>` element within the same `<place>` element.

**Example**
```xml
<cpfDescription>
    <identity>
        <entityType value="corporateBody"/>
        <nameEntry status="authorized" languageOfElement="eng">
            <part>International Council on Archives</part>
        </nameEntry>
        <nameEntry status="authorized" languageOfElement="fre">
            <part>Conseil International des Archives</part>
        </nameEntry>
    </identity>
    <description>
        <places>
            <place>
                <placeName vocabularySource="GeoNames" 
                vocabularySourceURI="https://www.geonames.org"
                valueURI="https://www.geonames.org/2988507/paris.html" countryCode="FR">
                Paris</placeName>
                <geographicCoordinates coordinateSystem="WGS84">
                48.8606298,2.3580453</geographicCoordinates>
                <address>
                    <addressLine addressLineType="country">France</addressLine>
                    <addressLine addressLineType="street" languageOfElement="fre">60 rue des
                    Francs-Bourgeois</addressLine>
                    <addressLine addressLineType="postalCode">75003</addressLine>
                    <addressLine addressLineType="district" languageOfElement="fre">3e
                    arrondissement</addressLine>
                    <addressLine addressLineType="district" languageOfElement="fre">
                    Haut-Marais</addressLine>
                    <addressLine addressLineType="region" languageOfElement="fre">
                    Île-de-France</addressLine>
                </address>
                <contact>
                    <contactLine contactLineType="phoneNumber">+33 (0)1 81 70 55 62
                    </contactLine>
                    <contactLine contactLineType="fax">+33 (0)1 81 70 55 61</contactLine>
                    <contactLine contactLineType="email" 
                    href="mailto:ica@ica.org">ica@ica.org</contactLine>
                    <contactLine contactLineType="homepage" 
                    href="https://www.ica.org/en">https://www.ica.org/en</contactLine>
                </contact>
                <placeRole vocabularySource="Wikidata" vocabularySourceURI="https://www.wikidata.org"
                valueURI="https://www.wikidata.org/wiki/Property:P159">
                Headquarters location</placeRole>
                <dateSet>
                    <dateRange>
                        <fromDate standardDate="1962-03-01">1 March 1962</fromDate>
                        <toDate standardDate="1978-07-15">15 July 1978</toDate>
                    </dateRange>
                    <dateRange>
                        <fromDate standardDate="1989-07-01">1 July 1989</fromDate>
                        <toDate status="ongoing"/>
                    </dateRange>
                </dateSet>
                <descriptiveNote>
                    <p>The headquarters has been at the National Archives of France in Paris
                           between 1962 and 1978. Afterwards it was moved just outside of Paris due
                           to extensive renovation works. Since 1989, the headquarters is again
                           located at rue des Francs-Bourgeois.</p>
                </descriptiveNote>
            </place>
        </places>
    </description>
</cpfDescription>
```
