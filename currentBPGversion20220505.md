<!-- Output copied to clipboard! -->

<!-- You have some errors, warnings, or alerts. If you are using reckless mode, turn it off to see inline alerts.
* ERRORs: 1
* WARNINGs: 0
* ALERTS: 1 -->

<p style="color: red; font-weight: bold">>>>>>  gd2md-html alert:  ERRORs: 1; WARNINGs: 1; ALERTS: 1.</p>
<ul style="color: red; font-weight: bold"><li>See top comment block for details on ERRORs and WARNINGs. <li>In the converted Markdown or HTML, search for inline alerts that start with >>>>>  gd2md-html alert:  for specific instances that need correction.</ul>

<p style="color: red; font-weight: bold">Links to alert messages:</p><a href="#gdcalert1">alert1</a>

<p style="color: red; font-weight: bold">>>>>> PLEASE check and correct alert issues and delete this message and the inline alerts.<hr></p>



# Best Practice Guide


## Society of American Archivists, Technical Subcommittee on Encoded Archival Standards

**Table of Contents**


[TOC]



# Introduction {#introduction}



* following ISAAR(CPF), not RiC-CM (yet)


# Dates {#dates}


## **Uncertain dates** {#uncertain-dates}

**Schema:** EAC-CPF

**Context:** Encoding uncertain dates in &lt;date>, &lt;toDate>, &lt;fromDate>

**Description:** 

The attributes @certainty, @notBefore and @notAfter can be used with the &lt;date>, &lt;toDate>, &lt;fromDate> elements to express the level of certainty of a particular date. @notBefore and @notAfter can be used to indicate the earliest and latest possible dates that an uncertain date might fall between. @certainty can be used to encode a term such as approximate, circa, or uncertain to indicate the level of certainty of the date provided. The @calendar and @era attributes are also available to provide additional information about a date.

EAC-CPF will also enable the use of the Extended Date/Time Format (EDTF), which has been included in the latest version of the ISO 8601 standard. This allows for the encoding of dates as '?', '~' and '%' ‘uncertain’ (?), ‘approximate’ (~), and ‘uncertain and approximate’ (%) within the machine-processable date in the @standardDate attribute for &lt;date>, &lt;fromDate> and &lt;toDate>.

**Examples: **

&lt;dateRange>


    &lt;fromDate notBefore="1971" notAfter="1975">around 1973&lt;/fromdate>


    &lt;toDate standardDate="1992">1992&lt;/toDate>

&lt;/dateRange>

&lt;date certainty="uncertain" standardDate="1968?">c. 1968&lt;/date> 

&lt;dateRange>


    &lt;fromDate calendar="gregorian" certainty="approximate" era="ce" standardDate="1950">1950&lt;/fromDate>


    &lt;toDate calendar="gregorian" certainty="approximate" era="ce" standardDate="2000">2000&lt;/toDate>

&lt;/dateRange>


## **Unknown or ongoing date ranges** {#unknown-or-ongoing-date-ranges}

**Schema:** EAC-CPF

**Context:** Encoding unknown or ongoing dates. 

**Description:** In some circumstances it may not be possible to include information about particular dates in an EAC-CPF instance because they are either unknown, or because a date range is ongoing. An example of an ongoing date range is a Corporate Body that continues to operate. Standalone dates may be unknown or a date range may be incomplete, for example when a date of birth is unknown. It may be important to indicate the status of these dates, rather than omitting them from the EAC-CPF instance. 

The @status attribute can be used with the &lt;date>, &lt;fromDate> and &lt;toDate> elements, with a controlled list of values, to allow for indicating where dates - or parts of a date range - may be unknown, or where a date range is ongoing. 

The available value for &lt;date> and &lt;fromDate> is "unknown", and the available values for &lt;toDate> are "unknown" or "ongoing"

**Examples: **

&lt;dateRange>

 	&lt;fromDate status="unknown"/>

&lt;toDate toDate certainty="uncertain" standardDate="2010?">c. 2010&lt;/toDate> 

&lt;/dateRange>

&lt;dateSet>


    &lt;date standardDate="2014-07">July 2014&lt;/date>


    &lt;dateRange>


        &lt;fromDate standardDate="2016-09">September 2016&lt;/fromDate>


         &lt;toDate status="ongoing"/>


    &lt;/dateRange>

&lt;/dateSet>

&lt;date status="unknown" />


# Names {#names}


## **Single name** {#single-name}

**Schema:** EAC-CFP

**Context:** Encoding a single name, if necessary with multiple name parts.

**Description:** Use a single &lt;nameEntry> element within &lt;identity> to enter a single name for an entity. Add attributes to define the names language, status, designation for display or other properties. 

Use the element &lt;part> to distinguish between parts of a name, if necessary.

Use the element &lt;useDates> to indicate the dates the name was used.

Use several elements &lt;nameEntry> within &lt;identity> when an entity used different names over time.

**Examples: **

&lt;nameEntry languageOfElement="de" preferredForm="true" status="authorized">

&lt;part localType="surname">Arendt&lt;/part>

&lt;part localType="firstname">Hannah&lt;/part>

&lt;/nameEntry>

&lt;nameEntry status="authorized">

&lt;part>Technical Subcommittee for Encoded Archival Standards&lt;/part>

&lt;useDates>


    &lt;dateRange>

                        		&lt;fromDate>2015&lt;/fromDate>

                        		&lt;toDate status="ongoing"/>

                    	&lt;/dateRange>

                &lt;/useDates>

&lt;/nameEntry>

&lt;nameEntry>

&lt;part>Noel family, Earls of Gainsborough&lt;/part>

&lt;/nameEntry>


## **Multiple names** {#multiple-names}

**Schema:** EAC-CPF

**Context:** Encoding multiple names for different forms of the same name.

**Description:** Bundle multiple elements &lt;nameEntry> within an element &lt;nameEntrySet> within &lt;identity> to enter different forms of the same name, e.g. official and alternative forms of a name, translations, transliterations, abbreviations, colloquial names etc. 

Add attributes in &lt;nameEntry>  to define the names language, status, designation for display or other properties. 

Use the element &lt;useDates> within the element &lt;nameEntrySet> to indicate the dates all names were used and use the same element with &lt;nameEntry> to indicate the date one of the names was used.

**Examples**: 

**&lt;nameEntrySet>**

**&lt;nameEntry** status="authorized">


    &lt;part localType="surname">Custer&lt;/part>

                    	&lt;part localType="firstname">Mark&lt;/part>

                &lt;/nameEntry>

                **&lt;nameEntry** status="alternative">

                    	&lt;part localType="GitHubName">fordmadox&lt;/part>

                    	&lt;useDates>

                	        	&lt;dateRange>

                            			&lt;fromDate>2011&lt;/fromDate>

                            		&lt;toDate status="ongoing"/>

              		          	&lt;/dateRange>

                    	&lt;/useDates>

                &lt;/nameEntry>

&lt;/nameEntrySet>


### **Qualify authorized and alternative names** {#qualify-authorized-and-alternative-names}

**Schema:** EAC-CPF

**Context:** Qualify a name entry as authorized or alternative name of an entity according to ISAAR(CPF)[^1] 5.1.2.

**Description:** Use the attribute @status for the element &lt;nameEntry> and select one of the given values "authorized" or "alternative" to indicate if a name is authorized or alternative. 

**Examples**: 

&lt;nameEntrySet>

**&lt;nameEntry status="authorized">**


    &lt;part localType="surname">Custer&lt;/part>

                    	&lt;part localType="firstname">Mark&lt;/part>

                &lt;/nameEntry>

                **&lt;nameEntry status="alternative">**

                    	&lt;part localType="GitHubName">fordmadox&lt;/part>

                    &lt;/nameEntry>

&lt;/nameEntrySet>


### **Reflect parallel usage according to cataloging rules in North America** {#reflect-parallel-usage-according-to-cataloging-rules-in-north-america}

**Schema:** EAC-CPF

**Context:** Qualify a set of name entries as parallel names according to cataloguing rules in North America.

**Description:** Use the attribute @localType with the value “parallel” within &lt;nameEntrySet> to reflect the usage of parallel names in North America. 

Use the attribute @localType in &lt;nameEntry> to specify the type of parallel name used, e.g. former, translation, abbreviation etc.

**Examples**: 

**&lt;nameEntrySet localType="parallel">**


        &lt;nameEntry languageOfElement="de" preferredForm="true" status="authorized" localType="native">

                        	&lt;part localType="surname">Arendt&lt;/part>

                        	&lt;part localType="firstname">Hannah&lt;/part>

&lt;/nameEntry>


        &lt;nameEntry languageOfElement="ja" scriptOfElement="Jpan" preferredForm="false" status="authorized" **localType="translation"**>

                        	&lt;part localType="surname">アーレント&lt;/part>

                        	&lt;part localType="firstname">ハナ&lt;/part>

                    &lt;/nameEntry>

                    &lt;nameEntry languageOfElement="en" preferredForm="false" status="authorized">

                        	&lt;part localType="surname">Arendt&lt;/part>

                        	&lt;part localType="firstname">Hannah&lt;/part>

                    &lt;/nameEntry>

&lt;/nameEntrySet>


### **Qualify a name as preferred name for display purposes** {#qualify-a-name-as-preferred-name-for-display-purposes}

**Schema:** EAC-CPF

**Context:** Qualify a name entry as preferred name for display purposes.

**Description:** An entity with multiple names needs one name as preferred name for display purposes. If there are multiple equal names over time, i.e. multiple &lt;nameEntry> elements as siblings and child elements of &lt;identity>, multiple preferred names are possible. If there are multiple forms of a name, i.e. multiple &lt;nameEntry> elements within &lt;nameEntrySet>, only one of the names should be declared as the preferred name for display purposes.

**Examples**: 

&lt;nameEntrySet localType="parallel">


        &lt;nameEntry languageOfElement="de" **preferredForm="true"** status="authorized" localType="native">

                        	&lt;part localType="surname">Arendt&lt;/part>

                        	&lt;part localType="firstname">Hannah&lt;/part>

&lt;/nameEntry>


        &lt;nameEntry languageOfElement="ja" scriptOfElement="Jpan" preferredForm="false" status="authorized" localType="translation">

                        	&lt;part localType="surname">アーレント&lt;/part>

                        	&lt;part localType="firstname">ハナ&lt;/part>

                    &lt;/nameEntry>

                    &lt;nameEntry languageOfElement="en" preferredForm="false" status="authorized">

                        	&lt;part localType="surname">Arendt&lt;/part>

                        	&lt;part localType="firstname">Hannah&lt;/part>

                    &lt;/nameEntry>

&lt;/nameEntrySet>


## **Encode the rules applied for the construction of the name** {#encode-the-rules-applied-for-the-construction-of-the-name}

**Schema:** EAC-CPF

**Context:** Record the national or international conventions or rules for an authorized name applied by the agency that created the entities description, cf. ISAAR(CPF)[^2] 5.1.2 and 5.4.3.

**Description:** Use the element &lt;conventionDeclaration> within &lt;control> to declare the rule(s)/convention(s) for an authorized name applied by the agency that created the entity's description. Use @id attribute in &lt;conventionDeclaration> to provide an option for direct link between described rule and the name. 

Use the attribute @conventionDeclarationReference within the element &lt;nameEntry> to link directly from the name to the rule.

**Examples**:

**&lt;conventionDeclaration id="cd1">**


        &lt;reference href="https://www.legifrance.gouv.fr/loda/id/JORFTEXT000033553530/">Décret n° 2016-1689 du 8 décembre 2016 fixant le nom, la composition et le chef-lieu des circonscriptions administratives régionales - Légifrance&lt;/reference>

    &lt;/conventionDeclaration>

    **&lt;conventionDeclaration id="cd2">**


        &lt;reference href="https://deliberation.maregionsud.fr/docs/ASSEMBLEEPLENIERE/2017/12/15/DELIBERATION/D0V0Q.pdf">DELIBERATION N° 17-1166, 15 DECEMBRE 2017&lt;/reference>

    &lt;/conventionDeclaration>

   ** &lt;conventionDeclaration id="cd3">**


        &lt;reference href="cnig.gouv.fr/wp-content/uploads/2015/03/CNT-site-collectivit%C3%A9s-fran%C3%A7aises.pdf">Commission nationale de toponymie: Collectivités territoriales françaises &lt;/reference>

    &lt;/conventionDeclaration>

&lt;nameEntrySet languageOfElement="fre">

            	&lt;nameEntry **conventionDeclarationReference="cd1"** preferredForm="true">

                	&lt;part>Provence-Alpes-Côte d'Azur&lt;/part>

            	&lt;/nameEntry>

            	&lt;nameEntry **conventionDeclarationReference="cd2"**>

                	&lt;part>Région Sud Provence-Alpes-Côte d'Azur&lt;/part>

            	&lt;/nameEntry>

            	&lt;nameEntry **conventionDeclarationReference="cd3"**>

                	&lt;part>Provence-Alpes-Côte-d'Azur&lt;/part>

            	&lt;/nameEntry>

&lt;/nameEntrySet>


# Relations {#relations}


## **General remarks on relation encoding** {#general-remarks-on-relation-encoding}

**Schema:** EAC-CPF

**Context:** The encoding of relationships describes the nature of a relationship between (at least) two entities. The relationship direction always points from the person, family or corporate body described in the EAC-CPF instance to the target entity.

**Description:** Statements about relationships are constituted by the following basic data components: 



* Name of the related entity
* Type of the related entity
* Type of the relationship
* Role of the related entity in a relationship
* Time or time frame of a relationship
* Place of a relationship
* Source of the relationship statement

All components have in common that values can be expressed as literals. It is, however, also desirable to encode the URI representing the literal (value) as well as both the authority / vocabulary source and its URI:



* Name of the authority / vocabulary source (literal)
* URI of the authority / vocabulary source (resource/URI)
* URI of the value (resource/URI)

**Examples**: see below


## **Relation to a resource** {#relation-to-a-resource}

         		CPF entity			targets			resource

**Schema:** EAC-CPF

**Context:** Describe the relationship between the entity described and a resource, like archival records, fonds, papers, publications etc.

**Description:** Use the wrapper element &lt;relation> to include all information about the related resource and the character of the relation. Use the required child element &lt;targetEntity> to provide 

a title or name of the related resource. Use the optional child element &lt;relationType> to specify the type of relation. Use the optional child element &lt;targetRole> to specify the role of the related entity. Use &lt;date>, &lt;dateRange>, or &lt;dateSet> for specifying the time period of the relationship and &lt;place> for relevant location information. &lt;descriptiveNote> may be included for more detailed specifications or explanations of the relationship.

If needed, use &lt;objectXMLWrap> to embed XML documenting the related entity from any (or no) namespace. 

**Examples**: 

&lt;relation>

&lt;targetEntity **targetType="resource"**>


    &lt;part>Mémorial du colonel Gustafsson. - 1829&lt;/part>


    &lt;/targetEntity>


    &lt;date>1829&lt;/date>


    &lt;relationType valueURI="https://www.ica.org/standards/RiC/ontology#isCreatorOf" vocabularySource="RiC-O" vocabularySourceURI="https://www.ica.org/standards/RiC/ontology">is creator of&lt;/relationType>


    &lt;targetRole>Publication&lt;/targetRole>

&lt;/relation>


## **Relation to a CPF entity ** {#relation-to-a-cpf-entity}


    CPF entity			targets			person, family or corporate body

**Schema:** EAC-CPF

**Context:** Describe the relationship between the entity described and a person, family or corporate body.

**Description:** Use the wrapper element &lt;relation> to include all information about the related entity and the character of the relation. Use the required child element &lt;targetEntity> to provide a

a name of the related entity. Use the optional child element &lt;relationType> to specify the type of relation. Use the optional child element &lt;targetRole> to specify the role of the related entity. Use &lt;date>, &lt;dateRange>, or &lt;dateSet> for specifying the time period of the relationship and &lt;place> for relevant location information. &lt;descriptiveNote> may be included for more detailed specifications or explanations of the relationship.

If needed, use &lt;objectXMLWrap> to embed XML documenting the related entity from any (or no) namespace. 

**Examples**: 

&lt;relation>

&lt;targetEntity targetType="person" valueURI="https://d-nb.info/gnd/120636123" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">


    &lt;part>Sophie&lt;/part>


    &lt;part>Baden, Großherzogin&lt;/part>


    &lt;/targetEntity>


    &lt;dateRange>


    &lt;fromDate>1801&lt;/fromDate>


    &lt;toDate>1865&lt;/toDate>


    &lt;/dateRange>

   	&lt;relationType valueURI="https://www.ica.org/standards/RiC/ontology#hasFamilyAssociationWith" vocabularySource="RiC-O" vocabularySourceURI="https://www.ica.org/standards/RiC/ontology">has family association with&lt;/relationType>

&lt;targetRole>daughter&lt;/targetRole>

&lt;/relation>


## **Relation to a function ** {#relation-to-a-function}


    CPF entity			targets				function

**Schema:** EAC-CPF

**Context:** Describe the relationship between the entity described and a function.

**Description:** Use the wrapper element &lt;relation> to include all information about the related function and the character of the relation. Use the required child element &lt;targetEntity> to provide a

a name or title of the related function. Use the optional child element &lt;relationType> to specify the type of relation. Use the optional child element &lt;targetRole> to specify the role of the related entity. Use &lt;date>, &lt;dateRange>, or &lt;dateSet> for specifying the time period of the relationship and &lt;place> for relevant location information. &lt;descriptiveNote> may be included for more detailed specifications or explanations of the relationship.

If needed, use &lt;objectXMLWrap> to embed XML documenting the related entity from any (or no) namespace. 

**Examples**: 


# References {#references}


## **Internal References** {#internal-references}

**Schema:** EAC-CPF

**Context: **Creating a reference from one element to another element in a single EAC-CPF instance.

**Description:** It is possible to create internal references from one element to another element within a single EAC-CPF instance. For example, you may wish to reference a detailed &lt;place> element from &lt;placename> elsewhere in the EAC-CPF instance. The @id and @target attributes are used to create these internal references.

The @id attribute is available on all elements to assign an identifier to an element that is unique within the instance. The @target attribute is available on all elements, except &lt;eac>, and can be used to refer to the @id of another element. To create the reference, use the @target attribute on the element you wish to create a reference from, and enter the value of the @id attribute on the element you wish to refer to, preceded by #. It is possible to refer to more than one element from a single element.

**Examples**: 

&lt;occupation>


    &lt;term>Assistant examiner - level III&lt;/term>


    &lt;placeName** target="#place1"**>Bern&lt;/placeName>

&lt;/occupation>

&lt;place** id="place1"**>


    &lt;placeName>Bern&lt;/placeName>


    &lt;placeRole>Place of work&lt;/placeRole>


    &lt;address>


        &lt;addressLine addressLineType="street">Stauffacherstrasse 65/59g&lt;/addressLine>


        &lt;addressLine addressLineType="postalCode">3003&lt;/addressLine>


        &lt;addressLine addressLineType="country">Switzerland&lt;/addressLine>


    &lt;/address>

&lt;/place>


## **Referencing external vocabularies, ontologies, etc.** {#referencing-external-vocabularies-ontologies-etc}

**Schema:** EAC-CPF

**Context:** Creating references to external vocabularies and ontologies from an EAC-CPF instance.

**Description:** The @valueURI, @vocabularySource and @vocabularySourceURI attributes are available on a number of elements for referencing external vocabularies or ontologies that have been used to populate the element.

@vocabularySource is used to identify a vocabulary that is the source of the element's value. @vocabularySourceURI is used for documenting a URI identifying the vocabulary source for the element's value. @valueURI is used for documenting a URI identifying the resource to be used as the element's value.

The attributes can be used individually, or combined to provide details about the source of the contents of an element, when an external vocabulary is being used.

**Examples**: 

&lt;place>


    &lt;placeName valueURI="https://d-nb.info/gnd/4005728-8" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">Berlin&lt;/placeName>		


    &lt;placeRole valueURI="https://d-nb.info/standards/elementset/gnd#placeOfBusiness" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Sitz&lt;/placeRole>

&lt;/place>


## **Referencing external sources** {#referencing-external-sources}

**Schema:** EAC-CPF

**Context:** Creating references to external sources from an EAC-CPF instance.

**Description:** To reference external sources for the contents of the EAC-CPF instance, encode the details of the external source in the &lt;control> sections, using the &lt;reference> element within &lt;source>. &lt;reference> is a required child element of &lt;conventionDeclaration>, &lt;localTypeDeclaration>, and &lt;rightsDeclaration> for identifying any rules and conventions applied in the compilation of the description. It is also a required child element of &lt;source>, used to identify any sources used in compiling the description. &lt;source> may include multiple child &lt;reference> elements.

&lt;reference> is an optional child element of &lt;abstract>, &lt;chronItem>, &lt;chronItemSet>, &lt;event>, &lt;eventDescription>, &lt;item>, and &lt;p> where it is used to reference any external resources that provide additional context to the contents of that element.

&lt;reference> can include an @href attribute to point to a specific address for a remote resource. 

**Examples**: 

&lt;source>

&lt;reference href="[https://catalog.archives.gov/search?q=*:*&f.oldScope=descriptions](https://catalog.archives.gov/search?q=*:*&f.oldScope=descriptions&f.level=series&f.locationIds=53023101)

[  &f.level=series&f.locationIds=53023101](https://catalog.archives.gov/search?q=*:*&f.oldScope=descriptions&f.level=series&f.locationIds=53023101)">Barack Obama Presidential Library&lt;/reference>

&lt;/source>

 

&lt;relation>


    &lt;targetEntity targetType="corporateBody">


    &lt;part>Democratic Party&lt;/part>


    &lt;/targetEntity>


    &lt;descriptiveNote>


        &lt;p>


        &lt;reference href="[https://en.wikipedia.org/wiki/](https://en.wikipedia.org/wiki/Barack_Obama)Barack_Obama">See more&lt;/reference>


        &lt;/p>


    &lt;/descriptiveNote>

&lt;/relation>


# Chronological list {#chronological-list}


## **Grouping events in a chronological list** {#grouping-events-in-a-chronological-list}

**Schema:** EAC-CPF

**Context:** Encoding two or more events and/or places within a timeline.

**Description:** Bundle multiple events &lt;event> and/or places &lt;place> within an element &lt;chronItemSet> within &lt;chronItem> to enter separate events occurring during a particular time period, e.g. multiple places visited in a particular timeframe understood better in a group than as separate occurrences. The example below contains itinerary data for a scientific expedition grouping multiple locations under distinct travel periods. Can be used to encode multiple event-based lists within a larger timeline.

Possible combinations include multiple events, a single event associated with multiple locations, multiple events associated with a single location, or multiple events associated with multiple locations. &lt;chronItemSet> may be repeated within &lt;chronItem> when necessary to associate multiple instances of such combinations with the date or dates recorded within &lt;chronItem>.

A number of attributes are available to qualify data such as language, source references, maintenance event references (to indicate the occurrence and agent responsible for the data), language encoding, and locally defined conventions.

&lt;chronItem> and &lt;chronItemSet> are subelements of &lt;chronList>, &lt;bioghist>, while &lt;description>. &lt;event>, &lt;place> and date elements are subelements of &lt;chronItem> and &lt;chronItemSet>. Refer to &lt;place> for attributes.

_Field work and expeditions in the early 20<sup>th</sup> century often involved harmful acts inflicted upon animals and communities for scientific research. While these practices are not conducted on large mammals today, historical events below are presented as they occurred or appear in evidentiary documentation._

**Examples**: 

&lt;chronList>

&lt;chronItem>


    &lt;date standardDate="1909-08-31">August 31, 1909&lt;/date>


    &lt;event>The party departs Naples, Italy via SS Adolph Woermann, where they are introduced to Sir Percy Girouard, the new British East Africa governor&lt;/event>


    &lt;place valueURI="[http://vocab.getty.edu/tgn/7004474](http://vocab.getty.edu/tgn/7004474)">Naples&lt;/placeEntry>

&lt;/chronItem>

**&lt;chronItem>**


    &lt;date standardDate="1909-09">September 1909&lt;/date>


    **&lt;chronItemSet>**


        &lt;event>Arrive in Mombasa, Sir Percy Girouard invites expedition party to travel by private rail to Nairobi&lt;/event>


        &lt;place valueURI="[http://vocab.getty.edu/tgn/7001115](http://vocab.getty.edu/tgn/7001115)">Mombasa&lt;/place>


        &lt;event>In Nairobi the party reconnects with old acquaintances and purchases supplies for the journey. /event>


        &lt;place valueURI ="[http://vocab.getty.edu/tgn/7001116](http://vocab.getty.edu/tgn/7001116)">Nairobi&lt;/place>


    &lt;/chronItemSet>

&lt;/chronItem>

**&lt;chronItem>**


    &lt;date standardDate="1909-10">October 1909&lt;/date>


        **&lt;chronItemSet** maintenanceEventReference="maintenancevent1" sourceReference="source1">


        &lt;event>Spent two weeks hunting rhino and lion, in the Lower Tana River Valley, Delia Akeley procures a small monkey and names her J.T. Jr.&lt;/event>


        &lt;place valueURI ="http://vocab.getty.edu/tgn/7593796">Tana River&lt;/place>


        &lt;event>Hunting elephants in Mt. Kenya&lt;/event>


        &lt;place valueURI ="[http://vocab.getty.edu/tgn/1105240](http://vocab.getty.edu/tgn/1105240)">Kirinyaga&lt;/place>


    &lt;/chronItemSet>

&lt;/chronItem> 

...

&lt;/chronList>


# Places and geographic features  {#places-and-geographic-features}


## **Naming places** {#naming-places}

**Schema:** EAC-CPF

**Context:** Encoding the name of a place in relation to other aspects of the entity description

**Description:** When describing a CPF entity, the description of this entity’s functions, activities, roles, occupations, mandates, etc. can play a vital role. In addition to simply naming such aspects, it furthermore can be useful to add a place dimension to them, e.g. when a person described has pursued their profession in various contexts and at several locations over time. Using the attributes @valueURI, @vocabularySource, and/or @vocabularySourceURI allows linking names of geographic locations in the element &lt;placeName> to external vocabularies and ontologies that might hold additional information such as name variations or geographic coordinates of the place. Similarly, one could use the attribute @target to point to the @id attribute of a &lt;place> element within the same EAC-CPF instance where more details about the named location have been provided.

**Examples**: 

&lt;cpfDescription>

    &lt;identity>

        &lt;entityType value="person"/>

        &lt;nameEntry status="authorized" languageOfElement="eng">

            &lt;part localType="firstname">Toni&lt;/part>

            &lt;part localType="lastname">Morrison&lt;/part>

        &lt;/nameEntry>

        &lt;nameEntry status="authorized" languageOfElement="eng">

            &lt;part localType="birthname">Chloe Ardelia Wofford&lt;/part>

        &lt;/nameEntry>

    &lt;/identity>

    &lt;description>

        &lt;occupations>

            &lt;!-- [...] -->

            &lt;occupation valueURI="https://www.wikidata.org/wiki/Q1622272"  \
            vocabularySource="Wikidata" vocabularySourceURI="https://www.wikidata.org">

                &lt;term>University teacher&lt;/term>

                &lt;placeName>Texas Southern University, Houston&lt;/placeName>

                &lt;placeName>Howard University, Washington, D.C.&lt;/placeName>

                &lt;placeName>State University of New York at Albany&lt;/placeName>

                &lt;placeName>New Brunswick campus, Rutger University, New Jersey&lt;/placeName>

                &lt;placeName>Bard College, Annandale-on-Hudson&lt;/placeName>

                &lt;placeName>Cornell University, Ithaca&lt;/placeName>

                &lt;placeName>Princeton University, Princeton&lt;/placeName>

            &lt;/occupation>

            &lt;!-- [...] -->

        &lt;/occupations>

    &lt;/description>

&lt;/cpfDescription>


## **Describing places** {#describing-places}

**Schema:** EAC-CPF

**Context:** Encoding the name of a place of relevance to the entity being described along with further details about the place

**Description:** Places tell a CPF entity’s story, might it be their place of birth or death, a place where they lived or worked, a place where an organization was established and made an impact. Places also provide anchor points linking one entity to another via the locations where their paths crossed. EAC-CPF enables a more detailed description of such places of relevance in the &lt;places>&lt;place> element within its &lt;description> section as well as in the context of a chronological list, e.g. for building a biography, and in the context of describing relationships between the entity being described and other entities. Next to naming a place using the element &lt;placeName>, describing a place also can include specification of the place’s role (&lt;placeRole>), address or contact details for a place (&lt;address>&lt;addressLine> and &lt;contact>&lt;contactLine> respectively) and geographic coordinates for a place (&lt;geographicCoordinates). At least one of these aspects has to be covered when describing a place. In addition, an optional date dimension can be added to places of relevance and more descriptive information can be added when describing places. 

When describing several places of relevance for the described entity, it is recommended to repeat the complete &lt;place> element and to make use of sub-elements such as &lt;placeRole>, &lt;address>, &lt;contact> or &lt;geographicCoordinates> in order to distinguish between the different places. For encoding variations of the name of a place, on the other hand, it is recommended to repeat only the &lt;placeName> element within the same &lt;place> element.

**Examples**: 

&lt;cpfDescription>

    &lt;identity>

        &lt;entityType value="corporateBody"/>

        &lt;nameEntry status="authorized" languageOfElement="eng">

            &lt;part>International Council on Archives&lt;/part>

        &lt;/nameEntry>

        &lt;nameEntry status="authorized" languageOfElement="fre">

            &lt;part>Conseil International des Archives&lt;/part>

        &lt;/nameEntry>

    &lt;/identity>

    &lt;description>

        &lt;places>

            &lt;place>

                &lt;placeName vocabularySource="GeoNames"  \
                vocabularySourceURI="https://www.geonames.org"

                valueURI="https://www.geonames.org/2988507/paris.html" countryCode="FR"> \
                Paris&lt;/placeName>

                &lt;geographicCoordinates coordinateSystem="WGS84"> \
                48.8606298,2.3580453&lt;/geographicCoordinates>

                &lt;address>

                    &lt;addressLine addressLineType="country">France&lt;/addressLine>

                    &lt;addressLine addressLineType="street" languageOfElement="fre">60 rue des

                    Francs-Bourgeois&lt;/addressLine>

                    &lt;addressLine addressLineType="postalCode">75003&lt;/addressLine>

                    &lt;addressLine addressLineType="district" languageOfElement="fre">3e

                    arrondissement&lt;/addressLine>

                    &lt;addressLine addressLineType="district" languageOfElement="fre"> \
                    Haut-Marais&lt;/addressLine>

                    &lt;addressLine addressLineType="region" languageOfElement="fre"> \
                    Île-de-France&lt;/addressLine>

                &lt;/address>

                &lt;contact>

                    &lt;contactLine contactLineType="phoneNumber">+33 (0)1 81 70 55 62 \
                    &lt;/contactLine>

                    &lt;contactLine contactLineType="fax">+33 (0)1 81 70 55 61&lt;/contactLine>

                    &lt;contactLine contactLineType="email"  \
                    href="mailto:ica@ica.org">ica@ica.org&lt;/contactLine>

                    &lt;contactLine contactLineType="homepage"  \
                    href="https://www.ica.org/en">https://www.ica.org/en&lt;/contactLine>

                &lt;/contact>

                &lt;placeRole vocabularySource="Wikidata" vocabularySourceURI="https://www.wikidata.org"

                valueURI="https://www.wikidata.org/wiki/Property:P159"> \
                Headquarters location&lt;/placeRole>

                &lt;dateSet>

                    &lt;dateRange>

                        &lt;fromDate standardDate="1962-03-01">1 March 1962&lt;/fromDate>

                        &lt;toDate standardDate="1978-07-15">15 July 1978&lt;/toDate>

                    &lt;/dateRange>

                    &lt;dateRange>

                        &lt;fromDate standardDate="1989-07-01">1 July 1989&lt;/fromDate>

                        &lt;toDate status="ongoing"/>

                    &lt;/dateRange>

                &lt;/dateSet>

                &lt;descriptiveNote>

                    &lt;p>The headquarters has been at the National Archives of France in Paris

                           between 1962 and 1978. Afterwards it was moved just outside of Paris due

                           to extensive renovation works. Since 1989, the headquarters is again

                           located at rue des Francs-Bourgeois.&lt;/p>

                &lt;/descriptiveNote>

            &lt;/place>

        &lt;/places>

    &lt;/description>

&lt;/cpfDescription>


# Locally defined value lists {#locally-defined-value-lists}


## **Defining a local value list to be used in the encoding** {#defining-a-local-value-list-to-be-used-in-the-encoding}

**Schema:** EAC-CPF

**Context:** Defining local conventions and value lists that are not present in an online vocabulary possible to enrich the descriptions. 

**Description:** When there are no possible on-line resources to link to for enriching the descriptions it is possible to use a locally defined convention or value list. You can use one or more locally defined conventions or value lists. The first step in making use of a local convention or value list is to declare the use of it in the encoding of the record in the &lt;control> section of the description. The element is named &lt;localTypeDeclaration> and with its help you can give a reference to it in combination with a possible short code or acronym that the convention or value list is known by and an descriptive note where the convention or value list can be described so the understanding of the used convention or value list is presented. The element itself is given an identification in the identification attribute in either the form of a short code or an identification code making it possible to reference the specific convention or value list used in the element throughout the whole description. The identification attribute helps to make sure that the used local type declaration is present in the description through validation functions found in the schema. It is worth noting that the identification attribute is of the type xml:id for making the validation possible and thus the rules for how identifications are created are enforced. The rules say that an Identification can not start with a number it needs to start with letters and may not contain spaces.

**Examples**: 

&lt;**localTypeDeclaration** id=”GNDO”>

&lt;reference href="[https://dnb.info/standards/elementset/gnd_20191015](https://dnb.info/standards/elementset/gnd_20191015)">


    GNDO


    &lt;/reference>

&lt;descriptiveNote>


    &lt;p>Gemeinsame Normdatei Ontologie&lt;/p>


    &lt;p languageOfElement="eng">Integrated Authority File Ontology&lt;/p>


    &lt;p>Version 2019-10-15&lt;/p>

&lt;/descriptiveNote>

&lt;/localTypeDeclaration>

&lt;**localTypeDeclaration** id=”ltd1”>  

	&lt;reference href="[http://nad.ra.se/static/termlistor/Kategorikoder.htm](http://nad.ra.se/static/termlistor/Kategorikoder.htm)">


    Category codes


    &lt;/reference>


    &lt;shortCode>Category codes&lt;/shortCode>

 	&lt;descriptiveNote>  

  		&lt;p>Codes for categorizing different types of authority records


        through organizational form, operation, function, archival organization etcetera.

 		&lt;/p>


    	&lt;p>The category codes used in Swedish NAD&lt;/p>


    	&lt;p>To be used in element function&lt;/p>

 	&lt;/descriptiveNote>

&lt;/localTypeDeclaration>


## **Using a local value list to be used in the encoding** {#using-a-local-value-list-to-be-used-in-the-encoding}

**Schema:** EAC-CPF

**Context:** Referencing a locally defined convention or value lists in the encoding. 

**Description:** When the local type declaration has been made it is possible in all elements where the local type attribute is available to reference the locally defined convention or value list. The step two of referencing is based upon the use of two attributes @localType and @localTypeDeclarationReference where the first gives the value or convention used and the second gives the reference to the local type declaration that has been used. The use of the @localTypeDeclarationReference assures that the local type declaration has been used by containing the identification of the declaration and it being checked through rules present in the schema by using xml:id and the identification reference mechanism.

**Examples**: 

&lt;nameEntry status="authorized">

&lt;part **localType**="[https://d-nb.info/standards/elementset/gnd#personalName](https://d-nb.info/standards/elementset/gnd#personalName)" 

**localTypeDeclarationReference**="GNDO">Arendt, Hannah&lt;/part>

&lt;part **localType**="[https://dnb.info/standards/elementset/gnd#dateOfBirthAndDeath](https://dnb.info/standards/elementset/gnd#dateOfBirthAndDeath)" 

**localTypeDeclarationReference**="GNDO">1906-1975&lt;/part>

&lt;/nameEntry>

&lt;function **localType**="1" **localTypeDeclarationReference**="ltd1">

&lt;term>stateAuthority&lt;/term>

&lt;descriptiveNote>

	&lt;p>En textuell beskrivning av organisationens verksamhetssektor&lt;/p>

&lt;/descriptiveNote>

&lt;/function>


# Lists as part of narrative description {#lists-as-part-of-narrative-description}


## **Simple lists for structuring** {#simple-lists-for-structuring}

**Schema:** EAC-CPF

**Context:** Using simple lists in the context of narrative description to structure information

**Description:** Elements such as &lt;biogHist>, &lt;structureOrGenealogy>, and &lt;generalContext> can hold more narrative description relating to the history and general context of the EAC-CPF entity being described, respectively relating to the administrative structure of a corporate body or the genealogy of a family. Next to simple paragraphs (&lt;p>) and - in the context of &lt;biogHist> - the more specific chronological lists (&lt;chronList>), which allow for capturing important dates and events in the life of an EAC-CPF entity, this also includes the option of creating lists (&lt;list>). These can be useful when encoding enumerations, e.g. a list of different stages in the career of a person or a list of different departments and teams within an organization. Each stage is then represented by an &lt;item> within the &lt;list>. The optional element &lt;head> can be used to include a title for the list, while the attribute @listType can be used to define whether the list would be “ordered”, i.e. numbered, or “unordered”, i.e. using symbols like bullets (●), squares (◼), or hyphens (-) for each list entry.

**Examples**: 

&lt;cpfDescription>

        &lt;identity>

            &lt;entityType value="person"/>

            &lt;nameEntry>

                &lt;part localType="firstname">Joan Ruth&lt;/part>

                &lt;part localType="birthname">Bader&lt;/part>

                &lt;part localType="lastname">Ginsburg&lt;/part>

            &lt;/nameEntry>

        &lt;/identity>

        &lt;description>

            &lt;!-- [...] -->

            &lt;biogHist>

                &lt;!-- [...] -->

                &lt;list listType="unordered">

                    &lt;head>Legal and academic career&lt;/head>

                    &lt;item>Clerkship for Judge Edmund L. Palmieri, U.S. District Court for the Southern District  \
                    of New York&lt;/item>

                    &lt;item>Research associate and associate director of the Columbia Law School Project on  \
                    International Procedure&lt;/item>

                    &lt;item>Professor at Rutgers Law School&lt;/item>

                    &lt;item>Co-founder of the Women's Rights Law Reporter&lt;/item>

                    &lt;item>Professor at Columbia Law School&lt;/item>

                    &lt;item>Fellow of the Center for Advanced Study in the Behavioral Sciences at Stanford  \
                    University&lt;/item>

                    &lt;item>Co-founder of the Women's Rights Project at the American Civil Liberties  \
                    Union&lt;/item>

                    &lt;item>Judge on the District of Columbia Circuit of the U.S. Court of Appeals&lt;/item>

                    &lt;item>Judge on the U.S. Supreme Court&lt;/item>

                &lt;/list>

            &lt;/biogHist>

        &lt;/description>

    &lt;/cpfDescription>

&lt;cpfDescription>

        &lt;identity>

            &lt;entityType value="corporateBody"/>

            &lt;nameEntry>

                &lt;part>United Nations&lt;/part>

            &lt;/nameEntry>

        &lt;/identity>

        &lt;description>

            &lt;!-- [...] -->

            &lt;structureOrGenealogy>

                &lt;!-- [...] -->

                &lt;list listType="unordered">

                    &lt;head>Principal organs&lt;/head>

                    &lt;item>The General Assembly&lt;/item>

                    &lt;item>The Security Council&lt;/item>

                    &lt;item>The Secretariat with th Secretary-General&lt;/item>

                    &lt;item>The Economic and Social Council&lt;/item>

                    &lt;item>The International Council of Justice&lt;/item>

                    &lt;item>The Trusteeship Council&lt;/item>

                &lt;/list>

            &lt;/structureOrGenealogy>

        &lt;/description>

    &lt;/cpfDescription>


## **Multi-level lists** {#multi-level-lists}

**Schema:** EAC-CPF

**Context:** Using multi-level lists in the context of narrative description to convey more complex structures

**Description:** Next to allowing for the use of repeated &lt;item> elements to create simple lists, the element &lt;list> can also be used recursively, i.e. &lt;list> can also include another &lt;list>. Such multi-level lists can be of help when encoding more complex structures, e.g. a table of content of a person’s main publication in &lt;biogHist> or in &lt;generalContext>, or a family tree or an organizational chart in the context of &lt;structureOrGenealogy>. Depending on the use case, there might be &lt;item> and &lt;list> elements next to each other within &lt;list>, e.g. when representing the person being described as an &lt;item> and including their children as &lt;item>-s within a nested &lt;list> on the same level. Especially with multi-level lists, the use of the optional element &lt;head> would be recommended to indicate the relation of each nested &lt;list> to their parent &lt;list> or to the main &lt;list> overall. 

**Examples**: 

&lt;cpfDescription>

        &lt;identity>

            &lt;entityType value="person"/>

            &lt;nameEntry>

                &lt;part localType="firstname">Johan Sebastian&lt;/part>

                &lt;part localType="lastname">Bach&lt;/part>

            &lt;/nameEntry>

        &lt;/identity>

        &lt;description>

            &lt;!-- [...] -->

            &lt;structureOrGenealogy>

                &lt;!-- [...] -->

                &lt;list listType="unordered">

                    &lt;head>Children of Johann Sebastian Bach and Maria Barbara Bach&lt;/head>

                    &lt;item>Catharina Dorothea Bach&lt;/item>

                    &lt;item>Wilhelm Friedemann Bach&lt;/item>

                    &lt;list>

                        &lt;head>Children of Wilhelm Friedemann Bach&lt;/head>

                        &lt;item>Friederica Sophia Bach&lt;/item>

                        &lt;item>Two sons who did not live past infancy&lt;/item>

                    &lt;/list>

                    &lt;item>Carl Philipp Emanuel Bach&lt;/item>

                    &lt;list>

                        &lt;head>Children of Carl Philipp Emanual Bach&lt;/head>

                        &lt;item>Johann Adam Bach&lt;/item>

                        &lt;item>Anna Carolina Philippina Bach&lt;/item>

                        &lt;item>Johann Sebastian Bach ("the Younger")&lt;/item>

                        &lt;item>Other children who did not live to adulthood&lt;/item>

                    &lt;/list>

                    &lt;item>Johann Gottfried Bernhard Bach&lt;/item>

                    &lt;item>Three more children who did not live to their first birthday&lt;/item>

                &lt;/list>

                &lt;list listType="unordered">

                    &lt;head>Children of Johann Sebastian Bach and Anna Magdalena Wilcken&lt;/head>

                    &lt;item>Gottfried Heinrich Bach&lt;/item>

                    &lt;item>Johann Christoph Friedrich Bach&lt;/item>

                    &lt;list>

                        &lt;head>Children of Johann Christoph Friedrich Bach&lt;/head>

                        &lt;item>Anna Philippiana Friederica Bach&lt;/item>

                        &lt;item>Wilhelm Friedrich Ernst Bach&lt;/item>

                        &lt;list>

                            &lt;head>Children of Wilhelm Friedrich Ernst Bach&lt;/head>

                            &lt;item>Carolina Auguste Wilhelmine Bach&lt;/item>

                            &lt;item>Juliane Friederica Bach&lt;/item>

                        &lt;/list>

                        &lt;item>Christine Luise Bach&lt;/item>

                    &lt;/list>

                    &lt;item>Johann Christian Bach&lt;/item>

                    &lt;item>Elisabeth Juliane Friederica Bach&lt;/item>

                    &lt;list>

                        &lt;head>Children of Elisabeth Juliane Friederica Bach&lt;/head>

                        &lt;item>Johann Sebastian Altnickol&lt;/item>

                    &lt;/list>

                    &lt;item>Johanna Carolina Bach&lt;/item>

                    &lt;item>Regina Susanna Bach&lt;/item>

                    &lt;item>Six more children who did not live to adulthood&lt;/item>

                &lt;/list>

            &lt;/structureOrGenealogy>

        &lt;/description>

    &lt;/cpfDescription>

&lt;cpfDescription>

        &lt;identity>

            &lt;entityType value="person"/>

            &lt;nameEntry>

                &lt;part localType="firstname">Charles Robert&lt;/part>

                &lt;part localType="lastname">Darwin&lt;/part>

            &lt;/nameEntry>

        &lt;/identity>

        &lt;description>

            &lt;!-- [...] -->

            &lt;generalContext>

                &lt;!-- [...] -->

                &lt;list listType="unordered">

                    &lt;head>The Origins of Species by Means of Natural Selection or The Preservation of  \
                    Favoured Races in the Struggle of Life, 6th edition, with additions and corrections, 1873 \
                    &lt;/head>

                    &lt;item>Additions and corrections, to the sixth edition&lt;/item>

                    &lt;item>Historical sketch&lt;/item>

                    &lt;item>Introduction&lt;/item>

                    &lt;item>Chapter I - Variation under Domestication&lt;/item>

                    &lt;list>

                        &lt;item>Causes of Variability&lt;/item>

                        &lt;item>Effects of Habit and the use or disuse of Parts&lt;/item>

                        &lt;item>Correlated Variation&lt;/item>

                        &lt;item>Inheritance&lt;/item>

                        &lt;item>Character of Domestic Varieties&lt;/item>

                        &lt;item>Difficulty of distinguishing between Varieties and Species&lt;/item>

                        &lt;item>Origin of Domestic Varieties from one or more Specie&lt;/item>

                        &lt;item>Domestic Pigeons, their Differences and Origin&lt;/item>

                        &lt;item>Principles of Selection, anciently followed, their Effects&lt;/item>

                        &lt;item>Methodical and Unconscious Selection&lt;/item>

                        &lt;item>Unknown Origin of our Domestic Productions&lt;/item>

                        &lt;item>Circumstances favourable to Man's power of Selection&lt;/item>

                    &lt;/list>

                    &lt;item>Chapter II - Variation under Nature&lt;/item>

                    &lt;list>

                        &lt;!-- [...] -->

                    &lt;/list>

                    &lt;item>Chapter III - Struggle for Existence&lt;/item>

                    &lt;list>

                        &lt;!-- [...] -->

                    &lt;/list>

                    &lt;!-- [...] -->

                    &lt;item>Chapter XV - Recapitulation and Conclusion&lt;/item>

                    &lt;list>

                        &lt;!-- [...] -->

                    &lt;/list>

                    &lt;item>Glossary of Scientific Terms&lt;/item>

                    &lt;item>Index&lt;/item>

                &lt;/list>

            &lt;/generalContext>

        &lt;/description>

    &lt;/cpfDescription>


# Entity types {#entity-types}


## **Default entity types** {#default-entity-types}

**Schema:** EAC-CPF

**Context:** Encoding the type of agent being described in an EAC-CPF instance

**Description:** Following the chapter _5.1.1 Type of entity_ in the [International Standard Archival Authority Record for Corporate Bodies, Persons, and Families](https://www.ica.org/sites/default/files/CBPS_Guidelines_ISAAR_Second-edition_EN.pdf) (ISAAR-CPF), EAC-CPF includes the element &lt;entityType> within the &lt;identity> section to define whether the entity being described is an organization of some kind, a person, or a family. Meant to provide a standardized anchor supporting interoperability across variations of local applications of EAC-CPF, &lt;entityType> itself cannot have text, but requires the attribute @value to be used with either “corporateBody”, or “person”, or “family”. These three types are designed to be mutually exclusive, so that &lt;entityType> also cannot be repeated.  

**Examples**: 

&lt;identity>

    &lt;entityType value="corporateBody"/>

    &lt;nameEntry status="authorized" languageOfElement="de">

        &lt;part>ICARus - Internationales Zentrum für Archivforschung&lt;/part>

    &lt;/nameEntry>

    &lt;nameEntry status="authorized" languageOfElement="en-gb">

        &lt;part>ICARus - International Centre for Archival Research&lt;/part>

    &lt;/nameEntry>

&lt;/identity>

&lt;control>

    [...]

    &lt;localTypeDeclaration id="GNDO">

        &lt;reference href="https://d-nb.info/standards/elementset/gnd">Gemeinsame Normdatei  \
        Ontology&lt;/reference>

        &lt;shortCode>GNDO&lt;/shortCode>

    &lt;/localTypeDeclaration>

&lt;/control>

&lt;cpfDescription>

    &lt;identity>

        &lt;entityType value="person"/>

        &lt;nameEntry status="authorized">

            &lt;part localType="https://d-nb.info/standards/elementset/gnd#personalName"  \
            localTypeDeclarationReference="GNDO">Gustaf IV Adolf&lt;/part>

            &lt;part localType="https://d-nb.info/standards/elementset/gnd#nameAddition"  \
            localTypeDeclarationReference="GNDO">Kung av Sverige&lt;/part>

        &lt;/nameEntry>

     &lt;/identity>

&lt;/cpfDescription>

&lt;control>

    [...]

    &lt;localTypeDeclaration id="MARC21_MainEntry_PersonalName">

        &lt;reference href="https://www.loc.gov/marc/bibliographic/bd100.html">MARC 21 Bibliographic  \
        Full 100 - Main Entry-Personal Name (NR)&lt;/reference>

        &lt;shortCode>MARC 21&lt;/shortCode>

    &lt;/localTypeDeclaration>

&lt;/control>

&lt;cpfDescription>

    &lt;identity>

        &lt;entityType value="family"/>		

        &lt;nameEntry status="authorized">

            &lt;part localType="100$a">Mozart&lt;/part>

            &lt;part localType="100$c">Familie : 17.-19. Jh.&lt;/part>

        &lt;/nameEntry>

    &lt;/identity>

&lt;/cpfDescription>


## **Alternative entity types** {#alternative-entity-types}

**Schema:** EAC-CPF

**Context:** Encoding alternative types of agent being described in an EAC-CPF instance

**Description:** Next to &lt;entityType>, EAC-CPF also includes the element &lt;otherEntityType>. With &lt;otherEntityType> it is possible e.g. to provide translations or specifications of the default values used in &lt;entityType> or to include related agent types from other standards such as Records in Contexts (RiC). 

Similar to the plural and singular elements used in the &lt;description> section (f.i. &lt;functions> and &lt;function> or &lt;occupations> and &lt;occupation>), &lt;otherEntityType> is used within a wrapper element &lt;otherEntityTypes> that also allows for a &lt;descriptiveNote> to be included to add details with regard to the alternative entity types given. 

&lt;otherEntityType> itself allows for the three vocabulary attributes (@valueURI, @vocabularySource, @vocabularySourceURI) and hence enables the connection to external vocabularies for the alternative agent type provided in &lt;otherEntityType>&lt;term>. Same as all other singular elements, &lt;otherEntityType> also comes with the optional sub-elements for date and place encoding, so that the alternative agent type can be bound to a specific timespan or location with regard to its use or applicability. This might e.g. be useful when a corporate body has changed its legal form over time and one would want to already emphasize this fact in the &lt;identity> section, next to a potential use of &lt;legalStatus> within the &lt;description> section. 

**Examples**: 

&lt;control>

    [...]

    &lt;localTypeDeclaration id="termType" target="termTypeLocal">

        &lt;reference>Types of terms&lt;/reference>

    &lt;/localTypeDeclaration>

    &lt;localControl id="termTypeLocal">

        &lt;term>translation&lt;/term>

        &lt;term>specification&lt;/term>

        &lt;term>relatedStandard&lt;/term>

    &lt;/localControl>

&lt;/control>

&lt;cpfDescription>

    &lt;identity>

        &lt;entityType value="corporateBody"/>

        &lt;nameEntry status="authorized" languageOfElement="de">

            &lt;part>ICARus - Internationales Zentrum für Archivforschung&lt;/part>

        &lt;/nameEntry>

        &lt;nameEntry status="authorized" languageOfElement="en-gb">

            &lt;part>ICARus - International Centre for Archival Research&lt;/part>

        &lt;/nameEntry>

        &lt;otherEntityTypes>

            &lt;otherEntityType localType="translation" localTypeDeclarationReference="termType"  \
            valueURI="https://d-nb.info/gnd/4128521-9" vocabularySource="GND">

                &lt;term language Of Element="de">Körperschaft&lt;/term>

            &lt;/otherEntityType>

            &lt;otherEntityType localType="specification" localTypeDeclarationReference="termType"  \
            valueURI="https://d-nb.info/gnd/4043774-7" vocabularySource="GND">

                &lt;term languageOfElement="de">Organisation&lt;/term>

            &lt;/otherEntityType>

            &lt;otherEntityType localType="specification" localTypeDeclarationReference="termType"  \
            valueURI="https://data.bnf.fr/ark:/12148/cb11951020r" vocabularySource="RAMEAU">

                &lt;term languageOfElement="fr">Organisation&lt;/term>

            &lt;/otherEntityType>

            &lt;otherEntityType localType="specification" localTypeDeclarationReference="termType"  \
            valueURI="https://d-nb.info/gnd/4293729-2" vocabularySource="GND">

                &lt;term languageOfElement="de">Nonprofit-Organisation&lt;/term>

            &lt;/otherEntityType>

            &lt;otherEntityType localType="specification" localTypeDeclarationReference="termType"  \
            valueURI="https://data.bnf.fr/ark:/12148/cb119498393" vocabularySource="RAMEAU">

                &lt;term languageOfElement="fr">Associations sans but lucratif&lt;/term>

            &lt;/otherEntityType>

            &lt;otherEntityType localType="specification" localTypeDeclarationReference="termType"  \
            valueURI="https://d-nb.info/gnd/4062714-7" vocabularySource="GND">

                &lt;term languageOfElement="de">Verein&lt;/term>

            &lt;/otherEntityType>

            &lt;otherEntityType localType="specification" localTypeDeclarationReference="termType"  \
            valueURI="https://data.bnf.fr/ark:/12148/cb13318322c" vocabularySource="RAMEAU">

                &lt;term languageOfElement="fr">Associations&lt;/term>

            &lt;/otherEntityType>

        &lt;/otherEntityTypes>

    &lt;/identity>

&lt;/cpfDescription>

&lt;control>

    [...]

    &lt;localTypeDeclaration id="GNDO">

        &lt;reference href="https://d-nb.info/standards/elementset/gnd">Gemeinsame Normdatei  \
        Ontology&lt;/reference>

        &lt;shortCode>GNDO&lt;/shortCode>

    &lt;/localTypeDeclaration>

   &lt;localTypeDeclaration id="termType" target="termTypeLocal">

        &lt;reference>Types of terms&lt;/reference>

    &lt;/localTypeDeclaration>

    &lt;localControl id="termTypeLocal">

        &lt;term>translation&lt;/term>

        &lt;term>specification&lt;/term>

        &lt;term>relatedStandard&lt;/term>

    &lt;/localControl>

&lt;/control>

&lt;cpfDescription>

    &lt;identity>

        &lt;entityType value="person"/>

        &lt;nameEntry status="authorized">

            &lt;part localType="https://d-nb.info/standards/elementset/gnd#personalName"  \
            localTypeDeclarationReference="GNDO">Gustaf IV Adolf&lt;/part>

            &lt;part localType="https://d-nb.info/standards/elementset/gnd#nameAddition"  \
            localTypeDeclarationReference="GNDO">Kung av Sverige&lt;/part>

        &lt;/nameEntry>

       &lt;otherEntityTypes>

           &lt;otherEntityType  \
           valueURI="https://d-nb.info/standards/elementset/gnd#RoyalOrMemberOfARoyalHouse"  \
           vocabularySource="GNDO"  \
           vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#"

           localType="specification" localTypeDeclarationReference="termType">

               &lt;term languageOfElement="ger">Regierender Fürst oder Mitglied eines regierenden  \
               Fürstenhauses&lt;/term>

            &lt;/otherEntityType>

        &lt;/otherEntityTypes>

    &lt;/identity>

&lt;/cpfDescription>

&lt;control>

    [...]

    &lt;localTypeDeclaration id="MARC21_MainEntry_PersonalName">

        &lt;reference href="https://www.loc.gov/marc/bibliographic/bd100.html">MARC 21 Bibliographic  \
        Full 100 - Main Entry-Personal Name (NR)&lt;/reference>

        &lt;shortCode>MARC 21&lt;/shortCode>

    &lt;/localTypeDeclaration>

&lt;/control>

&lt;cpfDescription>

    &lt;identity>

        &lt;entityType value="family"/>		

        &lt;nameEntry status="authorized">

            &lt;part localType="100$a">Mozart&lt;/part>

            &lt;part localType="100$c">Familie : 17.-19. Jh.&lt;/part>

        &lt;/nameEntry>

        &lt;otherEntityTypes>

            &lt;otherEntityType languageOfElement="eng"  \
            valueURI="https://www.ica.org/standards/RiC/ontology#Agent" vocabularySource="RiC-O"  \
            vocabularySourceURI="https://www.ica.org/standards/RiC/ontology">

                &lt;term>Agent&lt;/term>

            &lt;/otherEntityType>

            &lt;otherEntityType languageOfElement="eng"  \
            valueURI="https://www.ica.org/standards/RiC/RiC-O_v0-2.html#Group"  \
            vocabularySource="RiC-O"  \
            vocabularySourceURI="https://www.ica.org/standards/RiC/ontology">

                &lt;term>Group&lt;/term>

            &lt;/otherEntityType>

            &lt;otherEntityType languageOfElement="eng"  \
            valueURI="https://www.ica.org/standards/RiC/RiC-O_v0-2.html#Family"  \
            vocabularySource="RiC-O"  \
            vocabularySourceURI="https://www.ica.org/standards/RiC/ontology">

                &lt;term>Family&lt;/term>

            &lt;/otherEntityType>

        &lt;/otherEntityTypes>

    &lt;/identity>

&lt;/cpfDescription>


# Identifiers {#identifiers}


## **General remarks on identifiers**

**Schema:** EAC-CPF

**Context:** Identifiers used as unambiguous references in local systems are needed to identify or to refer to records, agencies, entities, resources, and authority files. There is a difference between identifiers for records and entities. 

**Description: **Different types of non-informational identifiers are used to identify 



* the present EAS instance within the element &lt;recordId>, cf. [Record identifiers](#record-identifiers)

    or to refer to

* other records of the same resource or entity as described in the EAS instance within the element &lt;otherRecordId>, cf. [Record identifiers](#record-identifiers)
* the agency, responsible for creation, maintenance or dissemination of the EAS instance within the element &lt;agencyCode>, c.f. [Agency Codes](#agency-codes)
* the entity, thus the person, family or corporate body, described the present EAC-CPF instance within the element &lt;identityId>, c.f. [Entity Identifiers](#entity-identifiers)
* the materials being described in an EAD instance within the element &lt;unidid>, c.f. ID of the Unit (coming soon)

**Examples**: see below


## **Record Identifiers**

**Schema:** EAC-CPF

**Context:** Unique identifier for the present EAS instance as globally unique identifier or as local identifier, but also unique identifier(s) for multiple records representing the same entity or resource in different systems. 

Record identifiers are associated with a record, not with the corporate body, person or familie, i.e. the entity, c.f. [entity identifier](#entity-identifiers).

**Description:** The present EAS instance needs a unique identifier within &lt;recordId>, a required, not repeatable and non-empty element in &lt;control>. The institution assigning the identifier ensures uniqueness of the &lt;recordId> value within the archival descriptions under its control. Depending on the records environment, it can be a locally unique identifier or a globally unique identifier.

Any alternative or additional record identifiers for the same EAS instance, local or authority file record may be recorded in &lt;otherRecordId>. Any merged, translated and aggregated records and also former or obsolete records are alternative records. Also use &lt;otherRecordId> to enter identifiers of different records in different systems for the same entity.

Use the attributes @valueURI, @vocabularySource and @vocabularySourceURI to link to the source of the other record identifier and to identify the source system, esp. when using an authority record. The attribute @localType can be used to identify the institution or service responsible for providing the associated record identifier, by name or identifier.

The URL for the EAC-CPF instance itself may be captured in &lt;representation>.

**Examples**: 


## **Agency Codes** {#agency-codes}

**Schema:** EAC-CPF

**Context:** Code or identifier for the institution or service responsible for the creation, maintenance, and/or dissemination of the EAS instance.

**Description:** Identify the institution or service responsible for the present EAS instance with a unique code or identifier preferably according to the [International Standard Identifier for Libraries](https://www.iso.org/standard/77849.html)

[and Related Organizations](https://www.iso.org/standard/77849.html) (ISIL), ISO 15511:2019, within the element &lt;agencyCode>. If this is not the case then local institution codes may be given with the ISO 3166-1 alpha-2 country code as the prefix to aim for international uniqueness.

Use the attribute @status with the value "authorized" or "alternative" to declare whether the agency code is using an authorized value, e.g. a registered ISIL code, or an alternative one.

Use &lt;otherAgencyCode> to record any alternative codes representing the agency.

**Examples**: 

&lt;maintenanceAgency>


    **&lt;agencyCode status="authorized" vocabularySource="ISIL" **vocabularySourceURI="http://id.loc.gov/vocabulary/identifiers/isil">US-ctybr&lt;/agencyCode>


    &lt;agencyName>Beinecke Rare Book and Manuscript Library&lt;/agencyName>


    **&lt;otherAgencyCode status="authorized"** valueURI="https://id.loc.gov/vocabulary/organizations/ctybr" vocabularySource="MARC Code List for Organizations" vocabularySourceURI="https://www.loc.gov/marc/organizations/">CtY-BR&lt;/otherAgencyCode>


    &lt;otherAgencyCode status="alternative" valueURI="https://www.wikidata.org/wiki/Q814779" vocabularySource="Wikidata" vocabularySourceURI="https://www.wikidata.org/"> Q814779&lt;/otherAgencyCode>

&lt;/maintenanceAgency>


## **Entity Identifiers** {#entity-identifiers}

**Schema:** EAC-CPF

**Context:** Identifier associated with the corporate body, person or familie, i.e. the entity, being described in the EAC-CPF instance.

**Description:** The repeatable element &lt;identityId> records identifiers such as legal identifiers, typically assigned by an authoritative agency. These identifiers can be (non exhaustive listing): business numbers, CAGE codes, Tax Identification numbers, personal registration numbers, passport numbers, ORCID ID, ISNI etc.

**Examples**: 


    &lt;identityId localType="RegistrationCode">222000-3103&lt;/identityId>


    &lt;identityId localType="VATRegistrationCode”>SE222000310301&lt;/identityId>


    &lt;identityId localType="EInvoiceID">2220003103&lt;/identityId>


# Control {#control}

Notes (SiJa):



* **conventionDeclaration**, languageDeclaration, localTypeDeclaration, rightsDeclaration 

 

**Schema:** EAS

**Context:** The control area contains information about the creation, maintenance, status and the rules and authorities used in the composition of the EAC-CPF instance.

**Description:** The element &lt;control> is a mandatory element in the root element &lt;eac>. It has 3 required child elements for the record identifier, the maintenance agency and for the maintenance history. Furthermore, the element &lt;control> needs the required attribute @maintenanceStatus to declare the current drafting status of the EAS instance.

The control area also includes information about sources of evidence, any used conventions and local types.

**Examples**: see below


## **Maintenance agency, history and status**

**Schema:** EAS

**Context:** The institution or service responsible for the EAS instance and the history of the creation and maintenance of this record that ends up in the status of the EAS instance.

**Description:** There is one institution or service, i.e. agency, responsible for the EAS instance and captured in the element &lt;maintenanceAgency>. For this agency one or more agency codes, preferably one agency code is an authorized ISIL code, can be given, c.f. [Agency Codes](#agency-codes). Additionally one or more names of the agency can be entered. At least one agency code or one agency name must be there to identify the maintenance agency.

The maintenance history must contain at least one maintenance event to record an activity in

the creation and unlimited more maintenance events to record the ongoing maintenance of an EAS instance, including revisions, updates, and deletions. 

So the element &lt;maintenanceHistory> has at least one child element &lt;maintenanceEvent> with information on the agent, in the child element &lt;agent>, that carried out the maintenance event, and the date and time the maintenance event occurred, in the child element &lt;eventDateTime>. The event might be described within &lt;eventDescription>.

The &lt;maintenanceEvent> can be used to enter information about origination and point in time of any assertion made in the EAS instance.

Add the attribute @id in &lt;maintenanceEvent> in order to identify this particular element. Use the attribute @maintenanceEventRefercence in any of the the elements of the identity area, the description area, and the relations allows for linking back to this particular element &lt;maintenanceEvent> in the current EAC-CPF instance.

**Examples**: 


    &lt;eac>

&lt;control maintenanceStatus="revised">


    &lt;recordId>record identifier&lt;/recordId>


    &lt;maintenanceAgency>


    &lt;agencyName>TS-EAS&lt;/agencyName>


    &lt;/maintenanceAgency>


    &lt;maintenanceHistory>


    &lt;maintenanceEvent maintenanceEventType="derived">


    &lt;agent agentType="machine">XSLT ead2cpf.xsl/Saxon B9&lt;/agent>


    &lt;eventDateTime standardDateTime="2009-08-30T09:37:17.029-04:00"/>


    &lt;eventDescription>Derived from EAD instance.&lt;/eventDescription>


    &lt;/maintenanceEvent>


    &lt;maintenanceEvent maintenanceEventType="revised">


    &lt;agent agentType="unknown"/>


    &lt;eventDateTime standardDateTime="2021-11-27"/>


    &lt;/maintenanceEvent>


    &lt;maintenanceEvent maintenanceEventType="updated">


    &lt;agent agentType="human">K. Bredenberg&lt;/agent>


    &lt;eventDateTime>December 2021&lt;/eventDateTime>


    &lt;/maintenanceEvent>


    &lt;/maintenanceHistory>

	&lt;/control> [...]


## **Sources of evidence**

**Schema:** EAC-CPF

**Context:** Source of evidence used for the establishment of the description of the CPF entity in the EAC-CPF instance.

**Description:** Within the element &lt;source> any source of evidence for any information within an EAC-CPF instance can be given. The element &lt;source> is repeatable within its plural element &lt;sources>.

Use the required child element &lt;reference> to include a textual identification of the reference, like author and title of a publication or article etc. In the case of online sources, use @href with &lt;reference> to provide a URI.

Use the optional child element &lt;citedRange> to point to a specific location within a source, like page numbers.

Use the optional &lt;descriptiveNote> for any additional notes about the source. 

Use the optional &lt;objectXMLWrap> to embed XML documenting the source from any namespace.

Add the attribute @id in &lt;source> in order to identify this particular element. Use the attribute @sourceReference in any of the the elements of the identity area, the description area, and the relations allows for linking back to this particular element &lt;source> in the current EAC-CPF instance.

Information given in the elements &lt;source> and &lt;maintenanceEvent>, cf. 

<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Maintenance agency, history and status"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Maintenance agency, history and status](#heading=h.pxymfnp10k), lay the foundation to the description of an assertion to the EAC-CPF description. 

**Examples**: 


    &lt;eac>

&lt;control maintenanceStatus="revised">[...]


    &lt;sources>


    &lt;source id=”SourceWiki”>


        &lt;reference href="https://de.wikipedia.org/wiki/Gustav_IV._Adolf_(Schweden)"> Wikipedia&lt;/reference>


    &lt;/source>


    &lt;source>


        &lt;reference href="https://sok.riksarkivet.se/sbl/Presentation.aspx?id=13318">Svenskt biografiskt lexikon&lt;/reference>


        &lt;descriptiveNote>


        &lt;p>Stand: 03.12.2020&lt;/p>


        &lt;/descriptiveNote>


    &lt;/source>


    &lt;/sources> [...]

&lt;/control> [...]


    &lt;/eac>


## 
    **Declarations in the control area**

**Schema: **EAC-CPF

**Context: **

**Description: **

**Examples: **


# Title {#title}

**Schema:** 

**Context:** 

**Description:** 

**Examples**: 


<!-- Footnotes themselves at the bottom. -->
## Notes

[^1]:
     ISAAR(CPF): International Standard Archival Authority Record for Corporate Bodies, Persons and Families. 
    Second Edition, 2004. (URL)

[^2]:
     ISAAR(CPF): International Standard Archival Authority Record for Corporate Bodies, Persons and Families. 
    Second Edition, 2004. (URL)
