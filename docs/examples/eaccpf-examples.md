---
layout: default
title: EAC-CPF xml
parent: Examples
nav_order: 1
---

# EAC-CPF xml
{: .no_toc }

## Table of Contents
{: .no_toc }

1. TOC
{:toc}

---

## Minimal record
# Example
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
