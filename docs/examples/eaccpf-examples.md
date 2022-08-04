---
layout: default
title: EAC-CPF xml
parent: Examples
nav_order: 1
---

# EAC-CPF xml
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Minimal record
**Example:**
[eaccpf-example-minimal.xml](https://github.com/SAA-SDT/EAS-Best-Practices/blob/main/_examples/eaccpf-example-minimal.xml)

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!-- EAC-CPF 2.0 example file prepared by TS EAS with a minimal mandatory set of elements and attributes -->
<eac xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xsi:schemaLocation="https://archivists.org/ns/eac/v2 https://eac.staatsbibliothek-berlin.de/schema/v2/eac.xsd"
 xmlns="https://archivists.org/ns/eac/v2">
    <control maintenanceStatus="new">
        <recordId>TS-EAS_EAC-CPF_2.0</recordId>
        <maintenanceAgency>
        <agencyName>TS-EAS</agencyName>
        </maintenanceAgency>
        <maintenanceHistory>
            <maintenanceEvent maintenanceEventType="created">
                <agent agentType="human">agent name</agent>
                <eventDateTime standardDateTime="2022-08-03"/>
            </maintenanceEvent>
        </maintenanceHistory>
    </control>
    <cpfDescription>
        <identity>
            <entityType value="person"/>
            <nameEntry>
                <part>full name of the entity</part>
            </nameEntry>
        </identity>
    </cpfDescription>
</eac>
```

## Extended record

**Example:**
[eaccpf-example-extended.xml](https://github.com/SAA-SDT/EAS-Best-Practices/blob/main/_examples/eaccpf-example-extended.xml)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!-- EAC-CPF 2.0 example file prepared by TS EAS extended with all possible elements and attributes -->
<eac xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xsi:schemaLocation="https://archivists.org/ns/eac/v2 https://eac.staatsbibliothek-berlin.de/schema/v2/eac.xsd"
 xmlns="https://archivists.org/ns/eac/v2" audience="internal" id="eaccpf1" languageOfElement="en"
 scriptOfElement="lat" base="baseURI">
    <control audience="external" base="baseURI" countryEncoding="iso3166-1" dateEncoding="iso8601"
        id="control1" languageEncoding="iso639-1" languageOfElement="en" maintenanceStatus="new"
        publicationStatus="inProcess" repositoryEncoding="iso15511" scriptEncoding="iso15924"
        scriptOfElement="lat" target="cpfDescription1">
        <recordId audience="external" id="recordid1" languageOfElement="en" scriptOfElement="lat"
            target="otherrecordid1">record identifier</recordId>
        <maintenanceAgency audience="external" countryCode="DE" id="maintenanceagency1"
            languageOfElement="eng" scriptOfElement="lat" target="maintenancehistory1"
            valueURI="agencyURI" vocabularySource="ISIL" vocabularySourceURI="ISILURI">
            <agencyCode audience="external" id="agencycode1" languageOfElement="eng"
                scriptOfElement="lat" status="authorized" target="agencyName1"
                valueURI="agencyCodeURI" vocabularySource="ISIL" vocabularySourceURI="ISILURI"
                >agency code</agencyCode>
            <agencyName audience="external" id="agencyName1" languageOfElement="eng"
                scriptOfElement="lat" valueURI="agencyNameURI" vocabularySource="VIAF"
                vocabularySourceURI="VIAFURI" target="agencycode1">agency name</agencyName>
            <otherAgencyCode audience="external" id="otherAgencyCode1" languageOfElement="eng"
                localType="localAgencyCode" localTypeDeclarationReference="ltd1"
                scriptOfElement="lat" status="alternative" valueURI="otherAgencyCodeURI"
                vocabularySource="VIAF" vocabularySourceURI="VIAFURI" target="maintenanceagency1"
                >other agency code</otherAgencyCode>
            <descriptiveNote>
                <p audience="external" conventionDeclarationReference="cd1" id="p1"
                    languageOfElement="en" maintenanceEventReference="me1" scriptOfElement="lat"
                    sourceReference="source1" target="maintenanceagency1">A generic element used
                    within other elements of &lt;description&gt; that marks one or more sentences
                    that form a logical prose passage. Repeat this element &lt;p&gt; in order to add
                    more paragraphs or translations.</p>
                <p>Information about the institution or service responsible for the creation,
                    maintenance, and/or dissemination of the EAC-CPF instance.</p>
            </descriptiveNote>
        </maintenanceAgency>
        <maintenanceHistory audience="external" id="maintenancehistory1" languageOfElement="de"
            scriptOfElement="lat" target="maintenanceagency1">
            <maintenanceEvent maintenanceEventType="updated">
                <agent agentType="human">TS-EAS team</agent>
                <eventDateTime standardDateTime="2022-08-03"/>
                <eventDescription>Update the example file after finalising schema</eventDescription>
            </maintenanceEvent>
            <maintenanceEvent maintenanceEventType="updated">
                <agent agentType="human">TS-EAS team</agent>
                <eventDateTime standardDateTime="2021-02-23"/>
                <eventDescription>Update the example file after finalising draft
                    schema</eventDescription>
            </maintenanceEvent>
            <maintenanceEvent audience="external" id="me1" languageOfElement="de"
                maintenanceEventType="created" scriptOfElement="lat" target="maintenancehistory1">
                <agent agentType="human" audience="external" id="agent1" languageOfElement="de"
                    scriptOfElement="lat" target="me1" valueURI="agentURI" vocabularySource="VIAF"
                    vocabularySourceURI="VIAFURI">agent name</agent>
                <eventDateTime audience="external" id="edt1" languageOfElement="de"
                    scriptOfElement="lat" standardDateTime="2020-07-01T13:01:48" target="me1"
                    >01.07.2020</eventDateTime>
                <eventDescription audience="external" id="eventdescription1" languageOfElement="de"
                    scriptOfElement="lat" target="me1">Record an activity in the creation and
                    ongoing maintenance of an EAC-CPF instance, including revisions, updates, and
                    deletions.</eventDescription>
            </maintenanceEvent>
            <maintenanceEvent maintenanceEventType="updated">
                <agent agentType="human">TS-EAS team</agent>
                <eventDateTime standardDateTime="2022-02-20"/>
                <eventDescription>Update the example file after finalising schema</eventDescription>
            </maintenanceEvent>
        </maintenanceHistory>
        <sources audience="external" base="baseURI" id="sources1" languageOfElement="eng"
            scriptOfElement="lat" target="control1">
            <source audience="external" id="source1" href="link to source" languageOfElement="eng"
                linkRole="linkrole" linkTitle="linktext" scriptOfElement="lat" target="sources1"
                valueURI="sourceURI" vocabularySource="sourcevocab"
                vocabularySourceURI="sourcevocabURI">
                <reference audience="external" conventionDeclarationReference="cd1"
                    href="externallink" id="reference1" languageOfElement="en" linkTitle="linktext"
                    linkRole="application/pdf" maintenanceEventReference="me1" scriptOfElement="lat"
                    sourceReference="source1" target="source1">external <span audience="external"
                        conventionDeclarationReference="cd1" id="sp1" languageOfElement="en"
                        localType="localspan" localTypeDeclarationReference="ltd1"
                        maintenanceEventReference="me1" sourceReference="source1"
                        scriptOfElement="lat" target="reference1" style="font-style:italic"
                        >reference</span> to a source</reference>
                <citedRange audience="external" id="citedRang1" languageOfElement="eng"
                    scriptOfElement="lat" target="reference1" unit="pagenumber">p. 1</citedRange>
                <descriptiveNote>
                    <p>descriptive note for a source</p>
                </descriptiveNote>
                <objectXMLWrap audience="internal" id="oxw1" target="source1">
                    <non-eas-xml xmlns="">
                        <etcetera/>
                    </non-eas-xml>
                </objectXMLWrap>
            </source>
            <descriptiveNote>
                <p>description for all sources</p>
            </descriptiveNote>
        </sources>
        <conventionDeclaration audience="external" id="cd1" languageOfElement="en"
            scriptOfElement="lat" target="control1" valueURI="conventionURI"
            vocabularySource="conventionvocab" vocabularySourceURI="conventionvocabURI">
            <reference>external reference to a rule or to a convention</reference>
            <shortCode audience="external" id="shortCode1" languageOfElement="en"
                scriptOfElement="lat" target="cd1">acronym, abbreviation or short code of the
                convention</shortCode>
            <descriptiveNote>
                <p>decriptive note for convention declaration</p>
            </descriptiveNote>
        </conventionDeclaration>
        <conventionDeclaration audience="external" id="cd2">
            <reference href="https://www.iso.org/standard/9029.html">Information and documentation -
                Romanization of Japanese</reference>
            <shortCode>DIN 32708:2014</shortCode>
            <descriptiveNote id="dn1">
                <p languageOfElement="de">Angewendet werden nur die eigentlichen Umschriftvorgaben,
                    nicht aber die Regeln zur Wortbildung in der lateinischen Umschrift. Diese
                    erfolgt analog der Praxis von NACSIS.</p>
            </descriptiveNote>
        </conventionDeclaration>
        <conventionDeclaration audience="external" id="cd3">
            <reference languageOfElement="fr">Indexation conforme à la norme: AFNOR. " AFNOR NF
                Z44-060 Documentation - Catalogage d'auteurs et d'anonymes: formes et structures des
                vedettes de collectivités - auteurs." Décembre 1996.</reference>
            <shortCode>AFNOR Z44-060</shortCode>
        </conventionDeclaration>
        <languageDeclaration audience="external" id="languageDeclaration1" languageOfElement="eng"
            languageCode="eng" scriptOfElement="lat" scriptCode="Lat" target="control1">
            <descriptiveNote>
                <p>language and script in which an EAC-CPF instance is written</p>
            </descriptiveNote>
        </languageDeclaration>
        <localControl audience="external" id="localControl1" languageOfElement="en"
            localType="localtype" localTypeDeclarationReference="ltd1" scriptOfElement="lat"
            target="control1" valueURI="localcontrolURI" vocabularySource="localcontrolvocab"
            vocabularySourceURI="localcontrolvocabURI">
            <term audience="external" conventionDeclarationReference="cd1" id="t1"
                languageOfElement="en" maintenanceEventReference="me1" scriptOfElement="lat"
                sourceReference="source1" target="localControl1">term for local control</term>
            <date audience="external" calendar="gregorian" certainty="circa"
                conventionDeclarationReference="cd1" era="ce" id="date1" languageOfElement="en"
                localType="localDate1" localTypeDeclarationReference="ltd1"
                maintenanceEventReference="me1" notAfter="2020" notBefore="2010"
                scriptOfElement="lat" sourceReference="source1" standardDate="2015"
                target="localControl1">date of local control</date>
        </localControl>
        <localTypeDeclaration audience="external" id="ltd1" languageOfElement="en"
            scriptOfElement="lat" target="control1" valueURI="localtypeURI"
            vocabularySource="localtypevocab" vocabularySourceURI="localtypevocabURI">
            <reference>external reference to the local type</reference>
            <shortCode>acronym, abbreviation or short code of the local type</shortCode>
            <descriptiveNote>
                <p>Local Type Declarations specifies the local conventions and controlled
                    vocabularies used in @localType attributes in the EAC-CPF instance.</p>
            </descriptiveNote>
        </localTypeDeclaration>
        <otherRecordId audience="external" id="otherrecordid1" languageOfElement="en"
            localType="localRecordId" localTypeDeclarationReference="ltd1" scriptOfElement="lat"
            valueURI="recordURI" vocabularySource="recordVocabulary"
            vocabularySourceURI="recordVocabularyURI" target="control1">other record
            identifier</otherRecordId>
        <representation audience="external" id="representation1" href="link to representation"
            languageOfElement="en" localType="localRepresentation"
            localTypeDeclarationReference="ltd1" linkRole="roleOfLink" linkTitle="linktext"
            scriptOfElement="lat" target="control1">text about representation; use case:
            https://snaccooperative.org/view/44995506</representation>
        <rightsDeclaration audience="external" id="rightsdeclaration1" languageOfElement="en"
            scriptOfElement="lat" target="control1" valueURI="rightsURI"
            vocabularySource="rightsvocab" vocabularySourceURI="rightsvocabURI">
            <reference>external reference to a license statement </reference>
            <shortCode>acronym, abbreviation or short code of the license statement </shortCode>
            <descriptiveNote>
                <p>descriptive note for rights declaration</p>
            </descriptiveNote>
        </rightsDeclaration>
    </control>
    <multipleIdentities audience="external" base="baseURI" id="multipleidentities1" target="eaccpf1">
        <cpfDescription audience="external" base="baseURI" conventionDeclarationReference="cd1"
            id="cpfDescription1" languageOfElement="eng" maintenanceEventReference="me1"
            scriptOfElement="lat" sourceReference="source1" target="control1">
            <identity audience="external" base="identiybaseURI" conventionDeclarationReference="cd1"
                id="identity1" identityType="given" languageOfElement="en" localType="localtype"
                localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                scriptOfElement="lat" sourceReference="source1" target="cpfDescription1">
                <entityType audience="external" id="entitytype1" value="family"/>
                <nameEntrySet audience="external" conventionDeclarationReference="cd1"
                    id="nameEntrySet1" languageOfElement="en" localType="localNameEntryset"
                    localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1" target="identity1">
                    <nameEntry audience="external" conventionDeclarationReference="cd1"
                        id="nameentry1" languageOfElement="en" localType="localtype"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        preferredForm="true" scriptOfElement="lat" sourceReference="source1"
                        status="authorized" target="nameEntrySet1" valueURI="http://nameURI"
                        vocabularySource="VIAF" vocabularySourceURI="VIAFUri">
                        <part audience="external" conventionDeclarationReference="cd1" id="part1"
                            languageOfElement="en" localType="localPart"
                            localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                            scriptOfElement="lat" sourceReference="source1" target="nameentry1">part
                            of name</part>
                        <useDates audience="external" conventionDeclarationReference="cd1"
                            id="useDates" languageOfElement="en" maintenanceEventReference="me1"
                            scriptOfElement="lat" sourceReference="source1" target="nameEntrySet1">
                            <dateSet audience="external" conventionDeclarationReference="cd1"
                                id="dateSet1" languageOfElement="en" localType="localDateSet"
                                localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                                scriptOfElement="lat" sourceReference="source1"
                                target="nameEntrySet1">
                                <dateRange>
                                    <fromDate standardDate="1947">1947</fromDate>
                                    <toDate standardDate="1949">1949</toDate>
                                </dateRange>
                                <date>1951</date>
                            </dateSet>
                        </useDates>
                    </nameEntry>
                    <nameEntry>
                        <part>another name entry</part>
                    </nameEntry>
                </nameEntrySet>
                <nameEntrySet localType="parallel">
                    <nameEntry languageOfElement="de" scriptOfElement="Latn" preferredForm="true"
                        status="authorized" localType="native">
                        <part localType="surname">Arendt</part>
                        <part localType="firstname">Hannah</part>
                    </nameEntry>
                    <nameEntry languageOfElement="ja" scriptOfElement="Jpan" preferredForm="false"
                        status="authorized" conventionDeclarationReference="cd1"
                        localType="translation">
                        <part localType="surname">アーレント</part>
                        <part localType="firstname">ハナ</part>
                    </nameEntry>
                    <nameEntry languageOfElement="en" scriptOfElement="Latn" preferredForm="false"
                        status="authorized">
                        <part localType="surname">Arendt</part>
                        <part localType="firstname">Hannah</part>
                    </nameEntry>
                    <useDates>
                        <dateRange>
                            <fromDate standardDate="1906">1906</fromDate>
                            <toDate standardDate="1975">1975</toDate>
                        </dateRange>
                    </useDates>
                </nameEntrySet>
                <nameEntrySet>
                    <nameEntry status="authorized">
                        <part localType="surname">Custer</part>
                        <part localType="firstname">Mark</part>
                    </nameEntry>
                    <nameEntry status="alternative">
                        <part localType="GitHubName">fordmadox</part>
                        <useDates>
                            <dateRange>
                                <fromDate>2011</fromDate>
                                <toDate status="ongoing"/>
                            </dateRange>
                        </useDates>
                    </nameEntry>
                </nameEntrySet>
                <nameEntry status="authorized">
                    <part>Technical Subcommittee for Encoded Archival Standards</part>
                    <useDates>
                        <dateRange>
                            <fromDate>2015</fromDate>
                            <toDate status="ongoing"/>
                        </dateRange>
                    </useDates>
                </nameEntry>
                <nameEntry>
                    <part>Noel family, Earls of Gainsborough</part>
                </nameEntry>
                <otherEntityTypes audience="external" conventionDeclarationReference="cd1"
                    id="otherentitytypes1" languageOfElement="en" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1" target="identity1">
                    <otherEntityType audience="external" conventionDeclarationReference="cd1"
                        id="otherEntityType1" languageOfElement="en" localType="localentitytype"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1" valueURI="http://valueURI"
                        vocabularySource="source" vocabularySourceURI="http://sourceURI"
                        target="otherentitytypes1">
                        <term>term for other entity type</term>
                        <date>date for other entity type</date>
                        <placeName audience="external" conventionDeclarationReference="cd1"
                            countryCode="DE" id="placeName1" languageOfElement="en"
                            localType="loacalplacetype1" localTypeDeclarationReference="ltd1"
                            maintenanceEventReference="me1" scriptOfElement="lat"
                            sourceReference="source1" target="otherentitytypes1"
                            valueURI="http://placeNameURI" vocabularySource="source"
                            vocabularySourceURI="http://sourceURI">place entry for other entity
                            type</placeName>
                        <descriptiveNote>
                            <p>descriptive note for other entity type</p>
                        </descriptiveNote>
                    </otherEntityType>
                    <otherEntityType>
                        <term>term for other entity type</term>
                    </otherEntityType>
                    <descriptiveNote>
                        <p>descriptive note for other entity types</p>
                    </descriptiveNote>
                </otherEntityTypes>
                <identityId audience="external" conventionDeclarationReference="cd1"
                    id="identityId1" languageOfElement="en" localType="localtype"
                    localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1"
                    vocabularySource="identityIdVocabulary"
                    vocabularySourceURI="http://identityIdVocabularyURI"
                    valueURI="https://identyIdURI" target="identity1">identity
                    identifier</identityId>
                <descriptiveNote audience="external" conventionDeclarationReference="cd1"
                    id="descriptivenote1" languageOfElement="en" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1" target="identity1">
                    <p>note for identity</p>
                </descriptiveNote>
            </identity>
            <description audience="external" base="baseURL" conventionDeclarationReference="cd1"
                id="description1" languageOfElement="en" maintenanceEventReference="me1"
                scriptOfElement="lat" sourceReference="source1" target="cpfDescription1">
                <demographicDescriptions audience="external" conventionDeclarationReference="cd1"
                    id="dds1" languageOfElement="en" localType="localdemographicdescriptions"
                    localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1" target="description1">
                    <demographicDescription audience="external" conventionDeclarationReference="cd1"
                        id="dd1" languageOfElement="en" localType="localdemographicdescriptions"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1" target="dds1"
                        valueURI="http://demographicvalue.org"
                        vocabularySource="demographicVocabulary"
                        vocabularySourceURI="http://demographicVocabulary.org">
                        <term>demographic information</term>
                        <date>date on demographic information</date>
                        <placeName>place related to demographic information</placeName>
                        <descriptiveNote>
                            <p>note on demographic information</p>
                        </descriptiveNote>
                    </demographicDescription>
                </demographicDescriptions>
                <functions audience="external" conventionDeclarationReference="cd1" id="fs1"
                    languageOfElement="en" localType="localfunctions"
                    localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1" target="description1">
                    <function audience="external" conventionDeclarationReference="cd1" id="f1"
                        languageOfElement="en" localType="localfunction"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1"
                        valueURI="http://functionvalue.org" vocabularySource="functionVocabulary"
                        vocabularySourceURI="http://functionVocabulary.org" target="fs1">
                        <term>function term</term>
                        <date>1950</date>
                        <descriptiveNote>
                            <p>descriptive note for this function</p>
                        </descriptiveNote>
                    </function>
                    <descriptiveNote>
                        <p>note for all functions</p>
                    </descriptiveNote>
                </functions>
                <languagesUsed audience="external" conventionDeclarationReference="cd1"
                    id="languagesused1" languageOfElement="en" localType="locallanguages"
                    localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1" target="description1">
                    <languageUsed audience="external" conventionDeclarationReference="cd1"
                        id="languageused1" languageOfElement="en" localType="locallanguage"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1" target="languagesused1">
                        <language audience="external" conventionDeclarationReference="cd1"
                            id="language1" languageCode="en" languageOfElement="en"
                            maintenanceEventReference="me1" scriptOfElement="lat"
                            sourceReference="source1" target="languageused1">English</language>
                        <writingSystem audience="external" conventionDeclarationReference="cd1"
                            id="script1" languageOfElement="en" maintenanceEventReference="me1"
                            scriptCode="lat" scriptOfElement="lat" sourceReference="source1"
                            target="languageused1">Latin</writingSystem>
                        <descriptiveNote>
                            <p>note for this information on used language and script</p>
                        </descriptiveNote>
                    </languageUsed>
                    <descriptiveNote>
                        <p>note for all used languages</p>
                    </descriptiveNote>
                </languagesUsed>
                <legalStatuses audience="external" conventionDeclarationReference="cd1"
                    id="legalStatuses1" languageOfElement="en" localType="locallegalstatuses"
                    localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1" target="description1">
                    <legalStatus audience="external" conventionDeclarationReference="cd1"
                        id="legalStatus1" languageOfElement="en" localType="locallegalstatus"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1"
                        valueURI="http://legalstatusterm.org"
                        vocabularySource="legalstatusvocaburlary"
                        vocabularySourceURI="http://legalstatusvocaburlary.org"
                        target="legalStatuses1">
                        <term>legal status term</term>
                        <date>1960</date>
                        <placeName>place related to a legal status</placeName>
                        <descriptiveNote>
                            <p>note for this legal status</p>
                        </descriptiveNote>
                    </legalStatus>
                    <descriptiveNote>
                        <p>note for all legal statuses</p>
                    </descriptiveNote>
                </legalStatuses>
                <localDescriptions audience="external" conventionDeclarationReference="cd1"
                    id="localDescriptions1" languageOfElement="en" localType="locallocaldeclaration"
                    localTypeDeclarationReference="ltd1"
                    maintenanceEventReference="maintenanceagency1" scriptOfElement="lat"
                    sourceReference="source1" target="description1">
                    <localDescription audience="external" conventionDeclarationReference="cd1"
                        id="localDescription1" languageOfElement="en"
                        localType="locallocaldeclaration" localTypeDeclarationReference="ltd1"
                        maintenanceEventReference="maintenanceagency1" scriptOfElement="lat"
                        sourceReference="source1" valueURI="http://localdescriptionterm.org"
                        vocabularySource="localvocabulary"
                        vocabularySourceURI="http://localvocabulary.org" target="localDescription1">
                        <term>term of a local description</term>
                        <date>1970</date>
                        <placeName>place related to a local description</placeName>
                        <descriptiveNote>
                            <p>Local Description provides a means to extend the list of description
                                elements specified in the EAC-CPF schema.</p>
                        </descriptiveNote>
                    </localDescription>
                    <descriptiveNote>
                        <p>note for all Local Descriptions.</p>
                    </descriptiveNote>
                </localDescriptions>
                <mandates audience="external" conventionDeclarationReference="cd1" id="mandates1"
                    languageOfElement="en" localType="localmandates"
                    localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1" target="description1">
                    <mandate audience="external" conventionDeclarationReference="cd1" id="mandate1"
                        languageOfElement="en" localType="localmandate"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1"
                        valueURI="http://mandateterm.org" vocabularySource="mandatetermsource"
                        vocabularySourceURI="http://mandatetermsource.org" target="mandates1">
                        <term>term of a mandate</term>
                        <date>1980</date>
                        <placeName>place related to this mandate</placeName>
                        <descriptiveNote>
                            <p>Used for identifying the source of authority or mandate for the
                                corporate body in terms of its powers, functions, responsibilities
                                or activities, such as a law, directive, or charter.</p>
                        </descriptiveNote>
                    </mandate>
                    <descriptiveNote>
                        <p>Groups together one or more occurrences of a mandate element.</p>
                    </descriptiveNote>
                </mandates>
                <occupations audience="external" conventionDeclarationReference="cd1"
                    id="occupations1" languageOfElement="en" localType="localoccupations"
                    localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1" target="description1">
                    <occupation audience="external" conventionDeclarationReference="cd1"
                        id="occupation1" languageOfElement="en" localType="localoccupation"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1"
                        valueURI="http://occupationterm.org" vocabularySource="occupationvocabulary"
                        vocabularySourceURI="http://occupationvocabulary.org" target="occupations1">
                        <term>term of an occupation</term>
                        <dateRange>
                            <fromDate>1960</fromDate>
                            <toDate>1970</toDate>
                        </dateRange>
                        <placeName>place related to an occupation</placeName>
                        <descriptiveNote>
                            <p>Identify an occupation held by the CPF entity.</p>
                        </descriptiveNote>
                    </occupation>
                    <descriptiveNote>
                        <p>Used for grouping together one or more occupation elements.</p>
                    </descriptiveNote>
                </occupations>
                <places audience="external" conventionDeclarationReference="cd1" id="places1"
                    languageOfElement="en" localType="localPlaces"
                    localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1" target="description1">
                    <place audience="external" conventionDeclarationReference="cd1" id="place1"
                        languageOfElement="en" localType="localplace"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1" target="places1"
                        valueURI="http://www.geonames.org/2950159/berlin.html"
                        vocabularySource="GeoNames" vocabularySourceURI="http://www.geonames.org">
                        <placeName audience="external" conventionDeclarationReference="cd1"
                            countryCode="DE" id="placename1" languageOfElement="en"
                            localType="localPlaceName" localTypeDeclarationReference="ltd1"
                            maintenanceEventReference="me1" scriptOfElement="lat"
                            sourceReference="source1" target="place1"
                            valueURI="http://www.geonames.org/7303381/rosslyn-chapel.html"
                            vocabularySource="GeoNames"
                            vocabularySourceURI="http://www.geonames.org">name of the
                            place</placeName>
                        <placeRole audience="external" conventionDeclarationReference="cd1"
                            id="placeRole1" languageOfElement="en" maintenanceEventReference="me1"
                            scriptOfElement="lat" sourceReference="source1"
                            valueURI="http://vocabularySource.uri/placeRole"
                            vocabularySourceURI="http://vocabularySource.uri"
                            vocabularySource="sourceofvocabulary">example place</placeRole>
                        <geographicCoordinates audience="external"
                            conventionDeclarationReference="cd1" coordinateSystem="WGS84"
                            id="geoco1" languageOfElement="lat" maintenanceEventReference="me1"
                            scriptOfElement="lat" sourceReference="source1" target="place1">N 52°
                            31' 27'', E 13° 24' 37''</geographicCoordinates>
                        <address audience="external" conventionDeclarationReference="cd1"
                            id="address1" languageOfElement="en" localType="localAdress"
                            localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                            scriptOfElement="lat" sourceReference="source1">
                            <addressLine audience="external" addressLineType="street"
                                conventionDeclarationReference="cd1" languageOfElement="en"
                                localType="localadressline" localTypeDeclarationReference="ltd1"
                                maintenanceEventReference="me1" id="adressline1"
                                scriptOfElement="lat" sourceReference="source1" target="address1"
                                >distinct address information</addressLine>
                            <addressLine>distinct address information</addressLine>
                        </address>
                        <contact audience="external" conventionDeclarationReference="cd1"
                            languageOfElement="en" localType="localcontact"
                            localTypeDeclarationReference="ltd1" id="contact1"
                            maintenanceEventReference="me1" scriptOfElement="lat"
                            sourceReference="source1" target="place1">
                            <contactLine audience="internal" contactLineType="fax"
                                conventionDeclarationReference="cd1" id="contactLine1"
                                languageOfElement="en" localType="localcontactline"
                                localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                                scriptOfElement="lat" sourceReference="source1" href="www.fax.com"
                                linkRole="fax" linkTitle="Fax" target="contact1">distinct contact
                                information</contactLine>
                        </contact>
                        <dateSet>
                            <date>1950</date>
                            <dateRange>
                                <fromDate>1970</fromDate>
                                <toDate status="ongoing"/>
                            </dateRange>
                        </dateSet>
                        <descriptiveNote>
                            <p>note for this place</p>
                        </descriptiveNote>
                    </place>
                    <place>
                        <placeName>another place</placeName>
                    </place>
                    <descriptiveNote>
                        <p>note for all places</p>
                    </descriptiveNote>
                </places>
                <biogHist audience="external" conventionDeclarationReference="cd1" id="biogHist1"
                    languageOfElement="en" localType="localBiogHist"
                    localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1">
                    <head audience="external" conventionDeclarationReference="cd1" id="h1"
                        languageOfElement="en" maintenanceEventReference="me1" scriptOfElement="lat"
                        sourceReference="source1" target="biogHist1">header of a biography or
                        history</head>
                    <abstract audience="external" conventionDeclarationReference="cd1"
                        id="abstract1" languageOfElement="en" localType="localAbstract"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1" target="biogHist1">brief
                            <span>summary</span> of the information contained within the <reference
                            href="https://biography.com">biography</reference> or history as a
                        whole</abstract>
                    <chronList audience="external" conventionDeclarationReference="cd1"
                        id="chronlist1" languageOfElement="en" localType="localChronList"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        target="biogHist1" scriptOfElement="lat" sourceReference="source1">
                        <chronItem audience="external" conventionDeclarationReference="cd1"
                            id="chronitem1" languageOfElement="en" localType="localChronItem"
                            localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                            target="chronlist1" sourceReference="source1" scriptOfElement="lat">
                            <date>date of a list item</date>
                            <chronItemSet audience="external" conventionDeclarationReference="cd1"
                                id="cis1" languageOfElement="en" maintenanceEventReference="me1"
                                target="chronitem1" sourceReference="source1" scriptOfElement="lat">
                                <event audience="external" conventionDeclarationReference="cd1"
                                    id="e1" languageOfElement="en" localType="localevent"
                                    localTypeDeclarationReference="ltd1"
                                    maintenanceEventReference="me1" scriptOfElement="lat"
                                    sourceReference="source1" target="cis1"
                                    valueURI="http://eventvalue.org" vocabularySource="eventvocab"
                                    vocabularySourceURI="http://eventvocab.org">event of the list
                                    item</event>
                                <event>another event of the list item</event>
                                <place>
                                    <placeName>place of the event or list item</placeName>
                                </place>
                                <reference href="">reference to chronology item set</reference>
                            </chronItemSet>
                            <reference href="http://www.eventoflistitem.org">reference to list item
                                event</reference>
                        </chronItem>
                        <chronItem>
                            <dateRange>
                                <fromDate>start date for a list item</fromDate>
                                <toDate>end date for a list item</toDate>
                            </dateRange>
                            <event>event of this chronology list item</event>
                            <place>
                                <placeName>place of the event or list item</placeName>
                            </place>
                        </chronItem>
                        <chronItem>
                            <dateSet>
                                <date>single date of the list item</date>
                                <dateRange>
                                    <fromDate>start date for a list item</fromDate>
                                    <toDate>end date for a list item</toDate>
                                </dateRange>
                            </dateSet>
                            <event>event of the list item</event>
                        </chronItem>
                    </chronList>
                    <list audience="external" conventionDeclarationReference="cd1" id="l1"
                        languageOfElement="en" listType="ordered" localType="locallist"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1"
                        style="list-style-type: decimal" target="chronitem1">
                        <item>list item</item>
                    </list>
                    <p><span style="font-style:bold">Header</span>extended desription of biography
                        or history</p>
                    <p>text with <reference href="https:externalLink.com">link to
                            reference</reference> in text</p>
                    <p>
                        <reference href="https:externalLink.com">link to reference</reference>
                    </p>
                </biogHist>
                <existDates audience="external" conventionDeclarationReference="cd1"
                    id="existDates1" languageOfElement="en" localType="existDates"
                    localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1" target="description1">
                    <dateRange audience="external" conventionDeclarationReference="cd1"
                        id="dateRange1" languageOfElement="en" localType="localDateRange1"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1" target="existDates1">
                        <fromDate audience="external" calendar="gregorian" certainty="circa"
                            conventionDeclarationReference="cd1" era="ce" id="fD1"
                            languageOfElement="en" localType="localFromDate"
                            localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                            notAfter="2019" notBefore="1900" scriptOfElement="lat"
                            sourceReference="source1" standardDate="2010-12-31" status="unknown"
                            target="dateRange1">start date of existence</fromDate>
                        <toDate audience="external" certainty="circa"
                            conventionDeclarationReference="cd1" id="toDate1" languageOfElement="en"
                            localType="localToDate" localTypeDeclarationReference="ltd1"
                            maintenanceEventReference="me1" notAfter="2019" notBefore="1900"
                            scriptOfElement="lat" sourceReference="source1"
                            standardDate="2010-12-31" status="ongoing" calendar="gregorian"
                            target="dateRange1" era="ce">end date of existence</toDate>
                    </dateRange>
                    <descriptiveNote>
                        <p>descriptive Note for dates of existence</p>
                    </descriptiveNote>
                </existDates>
                <generalContext audience="external" conventionDeclarationReference="cd1" id="gc1"
                    languageOfElement="en" localType="localcontext"
                    localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1" target="description1">
                    <head>header of a general context description</head>
                    <p>Description of the general social and cultural context of the CPF entity
                        being described.</p>
                    <p>A discursive expression of the general context may be encoded as one or more
                        paragraph elements.</p>
                    <list listType="unordered" style="circle">
                        <item audience="external" conventionDeclarationReference="cd1" id="i1"
                            languageOfElement="en" localType="localitem"
                            localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                            scriptOfElement="lat" sourceReference="source1" target="gc1">list item,
                            unordered with circle</item>
                        <item>list item, unorded with circle</item>
                    </list>
                    <list listType="ordered">
                        <item>first list item</item>
                        <item>second list item</item>
                    </list>
                    <list>
                        <item>list or tree for the general context information</item>
                    </list>
                </generalContext>
                <structureOrGenealogy audience="external" conventionDeclarationReference="cd1"
                    id="structure1" languageOfElement="en" localType="localgenealogy"
                    localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                    scriptOfElement="lat" sourceReference="source1" target="description1">
                    <head>header of a structure or genealogy</head>
                    <p>Description of the internal administrative structure(s) of a corporate body
                        or the genealogy of a family.</p>
                    <list>
                        <item>item for a structure</item>
                    </list>
                </structureOrGenealogy>
            </description>
            <relations audience="external" base="baseURI" conventionDeclarationReference="cd1"
                id="relations1" languageOfElement="en" maintenanceEventReference="me1"
                scriptOfElement="lat" sourceReference="source1" target="cpfDescription1">
                <relation audience="external" conventionDeclarationReference="cd1" id="relation1"
                    languageOfElement="en" maintenanceEventReference="me1" scriptOfElement="lat"
                    sourceReference="source1" target="relations1">
                    <targetEntity audience="external" conventionDeclarationReference="cd1"
                        id="targetEntity1" languageOfElement="en" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1" valueURI="http://entity.uri"
                        vocabularySource="sourceofentityvoc"
                        vocabularySourceURI="http://sourceofentityvoc.org" targetType="person"
                        target="relation1">
                        <part>name or part of the name or term of the related entity</part>
                    </targetEntity>
                    <dateSet>
                        <date>1800</date>
                        <dateRange>
                            <fromDate>1900</fromDate>
                            <toDate>1950</toDate>
                        </dateRange>
                    </dateSet>
                    <relationType audience="external" conventionDeclarationReference="cd1"
                        id="relationtype1" languageOfElement="en" localType="localrelationtye"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1" vocabularySource="GND"
                        vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#"
                        valueURI="https://d-nb.info/standards/elementset/gnd#Family"
                        >Family</relationType>
                    <targetRole audience="external" conventionDeclarationReference="cd1"
                        id="targetRole1" languageOfElement="lat" localType="localtargetrole"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1"
                        vocabularySource="schema.org" vocabularySourceURI="http://schema.org"
                        valueURI="http://schema.org/parent" target="relation1">Parent</targetRole>
                    <place>
                        <placeName>place of the relation</placeName>
                        <placeRole>residence</placeRole>
                        <date>1930</date>
                        <descriptiveNote>
                            <p>descriptive note to a place related with the target entity</p>
                        </descriptiveNote>
                    </place>
                    <descriptiveNote>
                        <p>note for this relation</p>
                    </descriptiveNote>
                    <objectXMLWrap>
                        <non-eas-xml xmlns="">
                            <etcetera/>
                        </non-eas-xml>
                    </objectXMLWrap>
                </relation>
                <descriptiveNote>
                    <p>note for all relations</p>
                </descriptiveNote>
            </relations>
            <alternativeSet audience="external" base="baseURI"
                conventionDeclarationReference="cpfDescription1" id="as1" languageOfElement="eng"
                maintenanceEventReference="me1" scriptOfElement="lat" sourceReference="source1"
                target="control1">
                <setComponent audience="external" conventionDeclarationReference="cd1"
                    href="www.externallink.com" id="sc1" languageOfElement="eng" linkRole=""
                    linkTitle="link" maintenanceEventReference="me1" scriptOfElement="lat"
                    sourceReference="source1" target="control1">
                    <componentEntry audience="external" conventionDeclarationReference="cd1"
                        id="ce1" languageOfElement="en" localType="localcomentenentry"
                        localTypeDeclarationReference="ltd1" maintenanceEventReference="me1"
                        scriptOfElement="lat" sourceReference="source1" target="sc1"
                        valueURI="componententryvalue" vocabularySourceURI="componententryvocab"
                        vocabularySource="http://componententryvocab.org">Alternative authority
                        record of the EAC-CPF instance being described to be referenced and
                        described, as well as allowing the inclusion of the entire encoding of such
                        alternative authority record in any XML format.</componentEntry>
                    <descriptiveNote>
                        <p>Note about the alternative authority record of the EAC-CPF instance.</p>
                    </descriptiveNote>
                    <objectXMLWrap>
                        <non-eas-xml xmlns="">
                            <anyElement/>
                        </non-eas-xml>
                    </objectXMLWrap>
                </setComponent>
            </alternativeSet>
        </cpfDescription>
        <cpfDescription audience="external" id="cpfdescription2">
            <identity>
                <entityType value="person"/>
                <nameEntry>
                    <part>name of the person</part>
                </nameEntry>
            </identity>
        </cpfDescription>
    </multipleIdentities>
</eac>
```

## Corporate body record

**Example:**
[eaccpf-matturbancenter.xml](https://github.com/SAA-SDT/EAS-Best-Practices/blob/main/_examples/eaccpf-matturbancenter.xml)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!-- EAC-CPF 2.0 example file prepared by TS EAS describing the Matt Urban Center -->
<eac xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xsi:schemaLocation="https://archivists.org/ns/eac/v2 https://eac.staatsbibliothek-berlin.de/schema/v2/eac.xsd"
 xmlns="https://archivists.org/ns/eac/v2" audience="external">  
  <control countryEncoding="iso3166-1" dateEncoding="iso8601" languageEncoding="iso639-2b"
    maintenanceStatus="new" publicationStatus="published" repositoryEncoding="iso15511"
    scriptEncoding="iso15924">
    <recordId>001</recordId>
    <maintenanceAgency>
      <agencyCode>NBuU-AR</agencyCode>
      <agencyName>University Archives</agencyName>
    </maintenanceAgency>
    <maintenanceHistory>
      <maintenanceEvent maintenanceEventType="created">
        <agent agentType="human">TS-EAS</agent>
        <eventDateTime standardDateTime="2021-12-16"/>
      </maintenanceEvent>
      <maintenanceEvent maintenanceEventType="updated">
        <agent agentType="human">TS-EAS</agent>
        <eventDateTime standardDateTime="2022-03-07"/>
      </maintenanceEvent>
    </maintenanceHistory>
    <conventionDeclaration>
      <reference href="https://www2.archivists.org/standards">Describing Archives: A Content
        Standard</reference>
      <shortCode>DACS</shortCode>
    </conventionDeclaration>
    <localTypeDeclaration id="AAT">
      <reference href="https://www.getty.edu/research/tools/vocabularies/aat/index.html"
        >AAT</reference>
      <descriptiveNote>
        <p>Art and Architecture Thesaurus</p>
      </descriptiveNote>
    </localTypeDeclaration>
  </control>
  <cpfDescription>
    <identity>
      <entityType value="corporateBody"/>
      <nameEntry scriptOfElement="Latn" languageOfElement="eng" status="authorized">
        <part localType="primary_name">Lt. Col. Matt Urban Human Services Center of Western New
          York</part>
        <useDates>
          <date localType="usage" standardDate="2000-11-11">2000 November 11</date>
        </useDates>
      </nameEntry>
      <nameEntry status="alternative">
        <part localType="primary_name">Matt Urban Center</part>
      </nameEntry>
      <nameEntry status="alternative">
        <part localType="primary_name">Polish Community Center</part>
        <useDates>
          <dateRange localType="usage">
            <fromDate standardDate="1976">1976</fromDate>
            <toDate standardDate="2000">2000</toDate>
          </dateRange>
        </useDates>
      </nameEntry>
    </identity>
    <description>
      <functions>
        <function valueURI="http://vocab.getty.edu/page/aat/300055433" vocabularySource="aat" vocabularySourceURI="https://www.getty.edu/research/tools/vocabularies/aat/">
          <term>community development</term>         
          <placeName target="IDPlaceName1">East Side (Buffalo, N.Y.)</placeName>
          <descriptiveNote>
            <p>The organization’s mission is to create programs to improve the quality of
              residential housing and develop projects to improve the East Side of Buffalo and
              Western New York.</p>
          </descriptiveNote>
        </function>
      </functions>
      <places>
        <place>
          <placeName vocabularySource="local" id="IDPlaceName1">East Side (Buffalo,
            N.Y.)</placeName>
          <geographicCoordinates coordinateSystem="WGS84">N 42°53′48" W
            78°50′2"</geographicCoordinates>
        </place>
      </places>
    </description>
  </cpfDescription>
</eac>
```

## Person record

**Example:**
[eaccpf-mozart.xml](https://github.com/SAA-SDT/EAS-Best-Practices/blob/main/_examples/eaccpf-mozart.xml)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!-- EAC-CPF 2.0 example file prepared by TS EAS describing Mozart -->
<eac xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xsi:schemaLocation="https://archivists.org/ns/eac/v2 https://eac.staatsbibliothek-berlin.de/schema/v2/eac.xsd"
 xmlns="https://archivists.org/ns/eac/v2" audience="external">
	<control countryEncoding="iso3166-1" dateEncoding="iso8601" languageEncoding="iso639-2b" maintenanceStatus="new"
		publicationStatus="published" repositoryEncoding="iso15511" scriptEncoding="iso15924">
		<recordId>https://kalliope-verbund.info/gnd/118584618</recordId>
		<maintenanceAgency countryCode="DE">
			<agencyCode status="authorized">DE-611</agencyCode>
			<agencyName>Staatsbibliothek zu Berlin - Preußischer Kulturbesitz, Kalliope-Verbund</agencyName>
			<agencyName languageOfElement="eng">Berlin State Library - Prussian Cultural Heritage, Kalliope Union Catalog</agencyName>
		</maintenanceAgency>
		<maintenanceHistory>
			<maintenanceEvent maintenanceEventType="created">
				<agent agentType="human">DE-101</agent>
				<eventDateTime standardDateTime="1988-07-01"/>
			</maintenanceEvent>
			<maintenanceEvent maintenanceEventType="revised">
				<agent agentType="human">1400</agent>
				<eventDateTime standardDateTime="2015-10-15"/>
			</maintenanceEvent>
		</maintenanceHistory>
		<sources>
			<source>
				<reference>Szb. Mozart-Lex.</reference>
			</source>
		</sources>
		<conventionDeclaration>
			<reference href="https://www.loc.gov/aba/rda/">Resource Description and Access</reference>
			<shortCode>RDA</shortCode>
		</conventionDeclaration>
		<languageDeclaration languageCode="ger" scriptCode="Latn"/>
		<localTypeDeclaration id="GNDO">
			<reference href="https://d-nb.info/standards/elementset/gnd_20191015">GNDO</reference>
			<descriptiveNote>
				<p>Gemeinsame Normdatei Ontologie</p>
				<p languageOfElement="eng">Integrated Authority File Ontology</p>
				<p>Version 2019-10-15</p>
			</descriptiveNote>
		</localTypeDeclaration>
<!-- Here we declare MARC21 System Control Number 035 and subfield Code a -->
		<localTypeDeclaration id="MARC21-035a">
			<reference href="https://www.loc.gov/marc/authority/ad035.html">MARC21: 035$a - System Control Number (R)</reference>
		</localTypeDeclaration>
<!-- Here we declare MARC21 System Control Number 035 and subfield Code z -->
		<localTypeDeclaration id="MARC21-035z">
			<reference href="https://www.loc.gov/marc/authority/ad035.html">MARC21: 035$z - Canceled/invalid system control number</reference>
		</localTypeDeclaration>
<!-- Here we refer to the valid authority file record number using the vocabulary of Gemeinsame Normdatei Ontology (GNDO) -->
		<otherRecordId vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#gndIdentifier" valueURI="http://d-nb.info/gnd/118584618">118584618</otherRecordId>
		<!-- Here we refer to an authority file record number using MARC21, originated by the German National Library (DE-101) and we link internally to the Local Type Declaration for 035$a of MARC21 -->
		<otherRecordId localType="035$a" localTypeDeclarationReference="MARC21-035a">(DE-101)118584618</otherRecordId>
		<!-- Here we refer to an authority file record number using the vocabulary of Gemeinsame Normdatei Ontology (GNDO), originated by Gemeinsame Normdatei (DE-588) -->
		<otherRecordId localType="035$a" localTypeDeclarationReference="MARC21-035a" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#gndIdentifier" valueURI="http://d-nb.info/gnd/118584618">(DE-588)118584618</otherRecordId>
		<!-- Here we refer to an invalid authority file record number using the vocabulary of Gemeinsame Normdatei Ontology (GNDO), originated by Personennormdatei (DE-588a) -->
		<otherRecordId localType="035$z" localTypeDeclarationReference="MARC21-035z" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#oldAuthorityNumber" valueURI="http://d-nb.info/gnd/118584618">(DE-588a)118584618</otherRecordId>	
		<!-- Here we refer to an invalid authority file record number using the vocabulary of Gemeinsame Normdatei Ontology (GNDO), originated by Schlagwort Normdatei (DE-588c) -->
		<otherRecordId localType="035$z" localTypeDeclarationReference="MARC21-035z" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#oldAuthorityNumber" valueURI="http://d-nb.info/gnd/4040426-2">(DE-588c)4040426-2</otherRecordId>
		<rightsDeclaration>
			<reference href="https://creativecommons.org/publicdomain/zero/1.0/deed.de">CC0 1.0 Universell</reference>
		</rightsDeclaration>
	</control>
	<cpfDescription>	
		<identity>
			<entityType value="family"/>		
			<nameEntry status="authorized">
				<part localType="100$a">Mozart</part>
				<part localType="100$c">Familie : 17.-19. Jh.</part>
			</nameEntry>
		</identity>
		<description>
			<localDescriptions>
				<localDescription localType="https://d-nb.info/standards/elementset/gnd#associatedDate" localTypeDeclarationReference="GNDO">
					<term>ca. 17. Jh.-19. Jh.</term>			
				</localDescription>
				<localDescription localType="https://d-nb.info/standards/elementset/gnd#broaderTermInstantial" localTypeDeclarationReference="GNDO" valueURI="https://d-nb.info/gnd/4016397-0" vocabularySource="GND"
					vocabularySourceURI="https://d-nb.info/standards/vocab/gnd/gnd-sc.html#">
					<term>Familie</term>
				</localDescription>				
				<localDescription localType="https://d-nb.info/standards/elementset/gnd#geographicAreaCode" localTypeDeclarationReference="GNDO" valueURI="https://d-nb.info/standards/vocab/gnd/geographic-area-code#XA-AT"
					vocabularySource="GND" vocabularySourceURI="https://d-nb.info/standards/vocab/gnd/geographic-area-code#">		
					<term>Österreich</term>
				</localDescription>
				<localDescription localType="https://d-nb.info/standards/elementset/gnd#geographicAreaCode" localTypeDeclarationReference="GNDO" valueURI="https://d-nb.info/standards/vocab/gnd/geographic-area-code#XA-DE"
					vocabularySource="GND" vocabularySourceURI="https://d-nb.info/standards/vocab/gnd/geographic-area-code#">
					<term>Deutschland</term>
				</localDescription>	
				<localDescription  localType="https://d-nb.info/standards/elementset/gnd#gndSubjectCategory" localTypeDeclarationReference="GNDO" valueURI="https://d-nb.info/standards/vocab/gnd/gnd-sc#14.4p"
					vocabularySource="GND" vocabularySourceURI="https://d-nb.info/standards/vocab/gnd/gnd-sc#">
					<term>Personen zu Musik</term>
				</localDescription>
				<localDescription  localType="https://d-nb.info/standards/elementset/gnd#gndSubjectCategory" localTypeDeclarationReference="GNDO" valueURI="https://d-nb.info/standards/vocab/gnd/gnd-sc.html#16.5p"
					vocabularySource="GND" vocabularySourceURI="https://d-nb.info/standards/vocab/gnd/gnd-sc.html#">
					<term>Personen der Geschichte (Politiker und historische Persönlichkeiten)</term>
				</localDescription>
			</localDescriptions>
			<places>
				<place>
					<placeName valueURI="https://d-nb.info/gnd/4076982-3" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">Salzburg</placeName>
					<placeRole valueURI="https://d-nb.info/standards/elementset/gnd#characteristicPlace" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Charakteristischer Ort</placeRole>
				</place>
				<place>
					<placeName valueURI="https://d-nb.info/gnd/4066009-6" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">Wien</placeName>	
					<placeRole valueURI="https://d-nb.info/standards/elementset/gnd#characteristicPlace" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Charakteristischer Ort</placeRole>
				</place>
				<place>
					<placeName valueURI="https://d-nb.info/gnd/4003614-5" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">Augsburg</placeName>	
					<placeRole valueURI="https://d-nb.info/standards/elementset/gnd#characteristicPlace" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Charakteristischer Ort</placeRole>
				</place>					
			</places>				
			<biogHist>
				<p>Österr. Musikerfamilie</p>
			</biogHist>					
		</description>
		<relations>
			<relation>
				<targetEntity targetType="family" valueURI="http://d-nb.info/gnd/118584618" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">
					<part>Mozart, Familie</part>
				</targetEntity>
				<relationType>Identity</relationType>
			</relation>
			<relation>
				<targetEntity targetType="person" valueURI="https://d-nb.info/gnd/1068251107" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">
					<part localType="https://d-nb.info/standards/elementset/gnd#personalName" localTypeDeclarationReference="GNDO">Mozart, Johann Georg</part>
					<part localType="https://d-nb.info/standards/elementset/gnd#dateOfBirthAndDeath" localTypeDeclarationReference="GNDO">1679-1736</part>
				</targetEntity>
				<relationType valueURI="https://d-nb.info/standards/elementset/gnd#memberOfTheFamily" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Familienmitglied</relationType>
			</relation>
			<relation>
				<targetEntity targetType="person" valueURI="https://d-nb.info/gnd/1068251859" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">
					<part localType="https://d-nb.info/standards/elementset/gnd#personalName" localTypeDeclarationReference="GNDO">Mozart, Anna Maria</part>
					<part localType="https://d-nb.info/standards/elementset/gnd#dateOfBirthAndDeath" localTypeDeclarationReference="GNDO">1696-1766</part>
				</targetEntity>
				<relationType valueURI="https://d-nb.info/standards/elementset/gnd#memberOfTheFamily" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Familienmitglied</relationType>
			</relation>				
			<relation>
				<targetEntity targetType="person" valueURI="https://d-nb.info/gnd/118584588" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">
					<part localType="https://d-nb.info/standards/elementset/gnd#personalName" localTypeDeclarationReference="GNDO">Mozart, Leopold</part>
					<part localType="https://d-nb.info/standards/elementset/gnd#dateOfBirthAndDeath" localTypeDeclarationReference="GNDO">1719-1787</part>
				</targetEntity>
				<relationType valueURI="https://d-nb.info/standards/elementset/gnd#memberOfTheFamily" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Familienmitglied</relationType>
			</relation>						
			<relation>
				<targetEntity targetType="person" valueURI="https://d-nb.info/gnd/119285428" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">
					<part localType="https://d-nb.info/standards/elementset/gnd#personalName" localTypeDeclarationReference="GNDO">Mozart, Anna Maria</part>
					<part localType="https://d-nb.info/standards/elementset/gnd#dateOfBirthAndDeath" localTypeDeclarationReference="GNDO">1720-1778</part>
				</targetEntity>
				<relationType valueURI="https://d-nb.info/standards/elementset/gnd#memberOfTheFamily" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Familienmitglied</relationType>
			</relation>					
			<relation>
				<targetEntity targetType="person" valueURI="https://d-nb.info/gnd/118584596" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">
					<part localType="https://d-nb.info/standards/elementset/gnd#personalName" localTypeDeclarationReference="GNDO">Mozart, Wolfgang Amadeus</part>
					<part localType="https://d-nb.info/standards/elementset/gnd#dateOfBirthAndDeath" localTypeDeclarationReference="GNDO">1756-1791</part>
				</targetEntity>
				<relationType valueURI="https://d-nb.info/standards/elementset/gnd#memberOfTheFamily" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Familienmitglied</relationType>
			</relation>				
			<relation>
				<targetEntity targetType="person" valueURI="https://d-nb.info/gnd/11858460X" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">
					<part localType="https://d-nb.info/standards/elementset/gnd#personalName" localTypeDeclarationReference="GNDO">Mozart, Maria Anna Walburga Ignatia</part>
					<part localType="https://d-nb.info/standards/elementset/gnd#dateOfBirthAndDeath" localTypeDeclarationReference="GNDO">1751-1829</part>
				</targetEntity>
				<relationType valueURI="https://d-nb.info/standards/elementset/gnd#memberOfTheFamily" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Familienmitglied</relationType>
			</relation>						
			<relation>
				<targetEntity targetType="person" valueURI="https://d-nb.info/gnd/11873721X" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">
					<part localType="https://d-nb.info/standards/elementset/gnd#personalName" localTypeDeclarationReference="GNDO">Mozart, Constanze</part>
					<part localType="https://d-nb.info/standards/elementset/gnd#dateOfBirthAndDeath" localTypeDeclarationReference="GNDO">1762-1842</part>
				</targetEntity>
				<relationType valueURI="https://d-nb.info/standards/elementset/gnd#memberOfTheFamily" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Familienmitglied</relationType>
			</relation>				
			<relation>
				<targetEntity targetType="person" valueURI="https://d-nb.info/gnd/119176653" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">
					<part localType="https://d-nb.info/standards/elementset/gnd#personalName" localTypeDeclarationReference="GNDO">Mozart, Franz Xaver Wolfgang</part>
					<part localType="https://d-nb.info/standards/elementset/gnd#dateOfBirthAndDeath" localTypeDeclarationReference="GNDO">1791-1844</part>
				</targetEntity>
				<relationType valueURI="https://d-nb.info/standards/elementset/gnd#memberOfTheFamily" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Familienmitglied</relationType>
			</relation>				
			<relation>
				<targetEntity targetType="person" valueURI="https://d-nb.info/gnd/117145114" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">
					<part localType="https://d-nb.info/standards/elementset/gnd#personalName" localTypeDeclarationReference="GNDO">Mozart, Carl</part>
					<part localType="https://d-nb.info/standards/elementset/gnd#dateOfBirthAndDeath" localTypeDeclarationReference="GNDO">1784-1858</part>
				</targetEntity>
				<relationType valueURI="https://d-nb.info/standards/elementset/gnd#memberOfTheFamily" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Familienmitglied</relationType>
			</relation>				
			<relation>
				<targetEntity targetType="person" valueURI="https://d-nb.info/gnd/122594967" vocabularySource="GND" vocabularySourceURI="https://d-nb.info/gnd/">
					<part localType="https://d-nb.info/standards/elementset/gnd#personalName" localTypeDeclarationReference="GNDO">Mozart, Maria Anna Thekla</part>
					<part localType="https://d-nb.info/standards/elementset/gnd#dateOfBirthAndDeath" localTypeDeclarationReference="GNDO">1758-1841</part>
				</targetEntity>
				<relationType valueURI="https://d-nb.info/standards/elementset/gnd#memberOfTheFamily" vocabularySource="GNDO" vocabularySourceURI="https://d-nb.info/standards/elementset/gnd#">Familienmitglied</relationType>
			</relation>		
		</relations>
	</cpfDescription>
</eac>
```
