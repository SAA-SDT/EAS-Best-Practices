---
layout: default
title: Describing places
parent: Places and geographic features
nav_order: 2
---

# Describing places

**Schema:**
Shared element in EAS

**Context:** 
Encoding the name of a place of relevance to the item being described along with further details about the place

**Description:** Places tell a CPF entity’s story, might it be their place of birth or death, a place where they lived or worked, a place where an organization was established and made an impact. Places also provide anchor points linking one entity to another via the locations where their paths crossed. 

`<place>` is a wrapper element available in `<description>` to encode information about a place or jurisdiction. This includes identifying the places or jurisdictions where the CPF entity was based, lived, or with which it had some other significant connection. At minimum, `<place>` requires the identification of the place using `<label>`. It can also be used to encode address and contact information as well as geographic coordinates; the role that the place has with regard to the entity described, e.g. birthplace; and the relationship between the place and the entity as well as a temporal dimension of that relationship. Associated date or date range ( `<date>` , `<dateRange>` , or `<dateSet>`) may be included to further constrain the place's meaning. A `<descriptiveNote>` may be included if a fuller explanation of the significance of the place to the CPF entity described is needed.

When describing several places of relevance for the described entity, it is recommended to repeat the complete `<place>` element and to make use of sub-elements such as `<address>`, `<geographicCoordinates>`, and `<role>` in order to distinguish between the different places. For encoding variations of the name of a place, it is recommended to repeat only the `<label>` element within the same `<place>` element.

**Example**
Note: The values for encoding address and contact information components in `@addressLineType` and `@contactLineType` are defined by `@addressLineTypeEncoding` and `@contactLineTypeEncoding` within `<control>`. The terms available for `@status` are defined by `@statusEncoding` within `<control>` and can vary by element, i.e., "ongoing" for `<toDate>`.
```xml
<control addressLineTypeEncoding="EASList" agentTypeEncoding="EASList" audienceEncoding="EASList"
 contactLineTypeEncoding="EASList" countryEncoding="iso3166-1-alpha-2" dateEncoding="iso8601"
 identityTypeEncoding="EASList" languageEncoding="iso639-2b" maintenanceStatus="revised"
 maintenanceEventTypeEncoding="EASList" maintenanceStatusEncoding="EASList" placeTypeEncoding="EASList"
 publicationStatus="published" publicationStatusEncoding="EASList" referredEntityTypeEncoding="EASList"
 relationTypeEncoding="EASList" repositoryEncoding="iso15511" scriptEncoding="iso15924"
 scriptOfElement="Latn" targetTypeEncoding="EASList" statusEncoding="EASList"> ...
</control>
...
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
      <label vocabularySource="GeoNames" vocabularySourceURI="https://www.geonames.org"
            valueURI="https://www.geonames.org/2988507/paris.html">Paris</label>
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
      <role vocabularySource="Wikidata" vocabularySourceURI="https://www.wikidata.org"
            valueURI="https://www.wikidata.org/wiki/Property:P159">Headquarters location</role>
      <geographicCoordinates coordinateSystem="WGS84">48.8606298,2.3580453</geographicCoordinates>
      <address>
        <addressLine addressLineType="country">France</addressLine>
        <addressLine addressLineType="street" languageOfElement="fre">60 rue des Francs-Bourgeois</addressLine>
        <addressLine addressLineType="postalCode">75003</addressLine>
        <addressLine addressLineType="district" languageOfElement="fre">3e arrondissement</addressLine>
        <addressLine addressLineType="district" languageOfElement="fre">Haut-Marais</addressLine>
        <addressLine addressLineType="region" languageOfElement="fre">Île-de-France</addressLine>
      </address>
      <contact>
        <contactLine contactLineType="phoneNumber">+33 (0)1 81 70 55 62 </contactLine>
        <contactLine contactLineType="fax">+33 (0)1 81 70 55 61</contactLine>
        <contactLine contactLineType="email" href="mailto:ica@ica.org">ica@ica.org</contactLine>
        <contactLine contactLineType="homepage" href="https://www.ica.org/en">https://www.ica.org/en</contactLine>
      </contact>
      <descriptiveNote>
        <p>The headquarters has been at the National Archives of France in Paris between 1962 and 1978. Afterwards it was moved just outside of Paris due to extensive renovation works. Since 1989, the headquarters is again located at rue des Francs-Bourgeois.</p>
      </descriptiveNote>
    </place>
  </places>
</description>
```