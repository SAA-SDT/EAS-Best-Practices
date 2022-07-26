---
layout: default
title: EAC-CPF Example Minimal
parent: _examples
nav_order: 1
---

# EAC-CPF Example Minimal

**Schema:** 
EAC-CPF


```xml
<?xml version="1.0" encoding="UTF-8"?>
<!-- EAC-CPF 2.0 example file minimal with a minimal mandatory set of elements and attributes -->
<eac xmlns="https://archivists.org/ns/eac/v2"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="https://github.com/SAA-SDT/eac-cpf-schema/blob/master/xml-schemas/eac-cpf/eac.xsd">
    <control maintenanceStatus="new">
        <recordId>TS-EAS_EAC-CPF_2.0</recordId>
        <maintenanceAgency>
        <agencyName>TS-EAS</agencyName>
        </maintenanceAgency>
        <maintenanceHistory>
            <maintenanceEvent maintenanceEventType="created">
                <agent agentType="human">SJagodzinski</agent>
                <eventDateTime standardDateTime="2022-02-20"/>
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
