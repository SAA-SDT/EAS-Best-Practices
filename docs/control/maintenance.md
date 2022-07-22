---
layout: default
title: Maintenance agency, history and status
parent: Control
nav_order: 1
---

# Maintenance agency, history and status

**Schema:** 
EAS

**Context:** 
The institution or service responsible for the EAS instance and the history of the creation and maintenance of this record that ends up in the status of the EAS instance.

**Description:** 
There is one institution or service, i.e. agency, responsible for the EAS instance and captured in the element `<maintenanceAgency>`. For this agency one or more agency codes, preferably one agency code is an authorized ISIL code, can be given, c.f. Agency Codes. Additionally one or more names of the agency can be entered. At least one agency code or one agency name must be there to identify the maintenance agency.

The maintenance history must contain at least one maintenance event to record an activity in the creation and unlimited more maintenance events to record the ongoing maintenance of an EAS instance, including revisions, updates, and deletions. So the element `<maintenanceHistory>` has at least one child element `<maintenanceEvent>` with information on the agent, in the child element `<agent>`, that carried out the maintenance event, and the date and time the maintenance event occurred, in the child element `<eventDateTime>`. The event might be described within `<eventDescription>`.

The `<maintenanceEvent>` can be used to enter information about origination and point in time of any assertion made in the EAS instance.

Add the attribute @id in <maintenanceEvent> in order to identify this particular element. Use the attribute @maintenanceEventReferecence in any of the the elements of the identity area, the description area, and the relations allows for linking back to this particular element `<maintenanceEvent>` in the current EAC-CPF instance.
  
**Examples**
```xml
<eac>
  <control maintenanceStatus="revised">
    <recordId>record identifier</recordId>
    <maintenanceAgency>
      <agencyName>TS-EAS</agencyName>
    </maintenanceAgency>
    <maintenanceHistory>
      <maintenanceEvent maintenanceEventType="derived">
        <agent agentType="machine">XSLT ead2cpf.xsl/Saxon B9</agent>
        <eventDateTime standardDateTime="2009-08-30T09:37:17.029-04:00"/>
        <eventDescription>Derived from EAD instance.</eventDescription>
      </maintenanceEvent>
      <maintenanceEvent maintenanceEventType="revised">
        <agent agentType="unknown"/>
        <eventDateTime standardDateTime="2021-11-27"/>
      </maintenanceEvent>
      <maintenanceEvent maintenanceEventType="updated">
        <agent agentType="human">K. Bredenberg</agent>
        <eventDateTime>December 2021</eventDateTime>
      </maintenanceEvent>
    </maintenanceHistory>
	</control> [...]
```
