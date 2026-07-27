---
layout: default
title: EAC-F Examples
parent: Functions
nav_order: 1
---

# EAC-F Example Applied to University Archives

**Schema:**
EAC-F

**Context:**
This example illustrates the use of EAC-F in archival records.

**Description:**
For this example, we show how the function of records is stable while the record-creating unit (agent) changes over time. The example used is on a function name of _Campus maintenance_. While records concerning and documenting campus maintenance may be created by different agents throughout time, the function itself as documented does not. In this example _Campus maintenance_ includes a full range of services to keep campus operational. Includes planning, construction, and operations in addition to custodial support, landscaping, snow removal, lockshop key services, and recycling assistance. We include function dates, agents, and relations to other records.

**Example**

```xml

<?xml version="1.0" encoding="UTF-8"?>
<?xml-model href="https://raw.githubusercontent.com/SAA-SDT/eas-schemas/refs/heads/release_2026_07/xml-schemas/eaf/eaf.nvdl" type="application/xml" schematypens="http://purl.oclc.org/dsdl/nvdl/ns/structure/1.0"?>
<?xml-model href="https://raw.githubusercontent.com/SAA-SDT/eas-schematron-validator/refs/heads/main/schematron/eaf.sch" type="application/xml" schematypens="http://purl.oclc.org/dsdl/schematron"?>
<eaf xmlns="https://standards.openpreservation.org/eaf/v1">
    <control>
        <recordId>Y1234</recordId>
        <maintenanceAgency>
            <agencyCode status="authorized">US-ctybr</agencyCode>
            <agencyName>Yale University, Beinecke Rare Book and Manuscript Library</agencyName>
        </maintenanceAgency>
        <maintenanceHistory>
            <maintenanceEvent maintenanceEventType="creation">
                <agent>
                    <label>Kolbe Resnick</label>
                    <role valueURI="https://vocab.getty.edu/aat/300162133">Archivist</role>
                </agent>
                <eventDateTime standardDateTime="2025-10-21">October 21, 2025</eventDateTime>
            </maintenanceEvent>
            <maintenanceEvent maintenanceEventType="derived">
                <agent>
                    <label>Elizabeth Roke</label>
                    <role  valueURI="https://vocab.getty.edu/aat/300162133">Archivist</role>
                </agent>
                <eventDateTime standardDateTime="2025-11-25">November 25, 2025</eventDateTime>
            </maintenanceEvent>
        </maintenanceHistory>
        <sources>
            <source href="https://www.yale.edu/board-trustees/governance-historic-documents/laws">
                <reference>Yale By-Laws</reference>
            </source>
        </sources>
        <conventionDeclaration id="relationType">
            <reference href="https://www.ica.org/standards/RiC/ontology"> Records in Contexts Ontology -
                Relationships properties </reference>
            <shortCode>RiC-O</shortCode>
        </conventionDeclaration>
    </control>
    <functionsDescription functionStatus="active">
        <identity>
            <nameEntry>
                <part>Campus maintenance</part>
                <useDates>
                    <dateRange>
                        <fromDate certainty="circa">1795</fromDate>
                        <toDate>2023</toDate>
                    </dateRange>
                </useDates>
            </nameEntry>
            <identityId>F96</identityId>
        </identity>
        <description>
            <functionAgents>
                <functionAgent valueURI="https://archives.yale.edu/agents/corporate_entities/9358">Buildings and Grounds Committee</functionAgent>
                <functionAgent valueURI="https://archives.yale.edu/agents/corporate_entities/10864">Office of Facilities</functionAgent>
            </functionAgents>
            <functionDates>
                <dateRange>
                    <fromDate certainty="circa">1795</fromDate>
                    <toDate>2023</toDate>
                </dateRange>
            </functionDates>
            <functionDescription>
                <p>Maintenance includes a full range of services to keep campus operational. Includes planning, construction, and operations in addition to custodial support, landscaping, snow removal, lockshop key services, and recycling assistance.
                </p>
            </functionDescription>
            <functionHistory>
                <p>Included with the first issuance of Yale’s by-laws in 1795, the care of the campus buildings and grounds has evolved with the University. From the 1750s until the early 1900s this included the Old Campus area including Connecticut Hall and the dormitories, expanding to encompass the Divinity School and Library between 1835-1849. Between 1870-1928, Yale expanded again and added residential colleges and the buildings that would make up the Gothic revival style buildings of Cross Campus. Today the library maintains swaths of green spaces and a wide range of architectural styles. Since 2005, the focus of facilities, construction, and maintenance projects have focused on energy and environmental sustainability, led by the Office of Sustainability.</p>
            </functionHistory>
            <legislations>
                <legislation>
                    <p>As approved by the Yale Corporation By-Laws: “The Committee on Buildings and Grounds shall consist of not fewer than five members of the Corporation. Persons with experience in fields relating to buildings and grounds, not members of the Corporation, may be invited to be members of the Committee without vote. Such members may be invited by the Corporation to serve for such terms as the Corporation may approve. It shall examine the proposals of the President to the Corporation concerning the development and maintenance of a capital plan; the priority of building needs; the location, design, and erection of new structures; and the upkeep and improvement of buildings and grounds; and shall make comments and recommendations with respect thereto, prior to the presentation of the proposals by the President to the Corporation. Before making recommendations to the Corporation which require expenditure of money not provided for in an approved budget, it shall submit its recommendations to the Committee on Finance for review and approval. The Committee shall establish policy with respect to the use of University residences and shall review and approve individually any proposals for capital maintenance or renovation of residences owned by the University and occupied by University officials.”
                    </p>
                    <date standardDate="2023-09-30">September 30, 2023</date>
                </legislation>
            </legislations>
        </description>
        <relations>
            <relation relationType="agent" targetType="https://www.ica.org/standards/RiC/ontology#isOrWasPerformedBy">
                <label valueURI="https://archives.yale.edu/agents/corporate_entities/9358">Yale University. Buildings and Grounds Committee</label>
            </relation>
            <relation relationType="agent" targetType="https://www.ica.org/standards/RiC/ontology#isOrWasPerformedBy">
                <label valueURI="https://archives.yale.edu/agents/corporate_entities/10864">Yale University. Office of Facilities</label>
            </relation>
            <relation relationType="function" targetType="https://www.ica.org/standards/RiC/ontology#isRelatedTo">
                <label>Environmental Sustainability</label>
                <descriptiveNote>
                    <p>Since 2005, the focus of facilities, construction, and maintenance projects have focused on energy and environmental sustainability, led by the Office of Sustainability.
                    </p>
                </descriptiveNote>
            </relation>
            <relation relationType="resource" targetType="https://www.ica.org/standards/RiC/ontology#resultsOrResultedIn">
                <label valueURI="https://archives.yale.edu/repositories/12/resources/2586">Yale University buildings and grounds architectural documentation</label>
            </relation>
            <relation relationType="resource" targetType="https://www.ica.org/standards/RiC/ontology#resultsOrResultedIn">
                <label valueURI="https://archives.yale.edu/repositories/12/resources/2871">Architectural drawings and maps of Yale University buildings and grounds</label>
            </relation>
            <relation relationType="resource" targetType="https://www.ica.org/standards/RiC/ontology#resultsOrResultedIn">
                <label valueURI="https://archives.yale.edu/repositories/12/resources/2090">Robin Winks, Buildings and Grounds Committee, Yale University, records</label>
                <descriptiveNote>
                    <p>Professor Robin Winks was a member of the Buildings and Grounds Committee from 1980-1984.</p>
                </descriptiveNote>
            </relation>
        </relations>
    </functionsDescription>
</eaf>
```