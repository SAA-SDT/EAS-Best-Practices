---
layout: default
title: maintenanceEventType
parent: EAS Value Lists
nav_order: 10
---

# maintenanceEvent

**Scope Note:**
To identify the type of maintenance activity. The terms below represent the action taken by an editor of a record. Resource consulted for value terms and scope notes include:

 - EAC-CPF 2.0 Tag Library, [https://eac.staatsbibliothek-berlin.de/schema/v2/eac.html#attr-maintenanceEventType](https://eac.staatsbibliothek-berlin.de/schema/v2/eac.html#attr-maintenanceEventType)

`@maintenanceEventType` is an attribute used to specify the maintenance activity in `<maintenanceEvent>`. Accepted values for `@maintenanceEventType` are listed below with scope notes. 

---

## cancelled

**Scope Note:**
Marks an instance as not current (obsolete or rejected), but retained for reference.

## created

**Scope Note:**
The initial creation of the EAS instance.

## deleted

**Scope Note:**
Indication that the instance has been deleted from the system.

## derived

**Scope Note:**
Indication that the instance was derived from another descriptive system.

## revised

**Scope Note:**
Any type of general modification to the EAS instance.

## unknown

**Scope Note:**
When the type of event is not known.

## updated

**Scope Note:**
When an instance has been brought up to date with significant changes to the entity's description or to the version of EAS used.
