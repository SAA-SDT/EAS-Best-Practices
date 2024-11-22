---
layout: default
title: maintenanceStatus
parent: EAS Value Lists
nav_order: 11
---

# maintenanceStatus

**Scope Note:**
To identify the current drafting status of the EAS instance (i.e., the status of the record, itself). Resource used for values and scope notes:
 - EAC-CPF 2.0 Tag Library, [https://eac.staatsbibliothek-berlin.de/schema/v2/eac.html#attr-maintenanceStatus](https://eac.staatsbibliothek-berlin.de/schema/v2/eac.html#attr-maintenanceStatus)

`@maintenanceStatus` is an attribute used in `<control>`. Accepted values for `@maintenanceStatus` are listed below with scope notes. 

---

## cancelled

**Scope Note:**
Record that is not current (obsolete or rejected) but kept for reference.

## deleted

**Scope Note:**
Record that has been deleted from the system.

## deletedMerged

**Scope Note:**
Record is deleted because it has been merged with another record.

## deletedReplaced

**Scope Note:**
Replaced by a new record.

## deletedSplit

**Scope Note:**
Deleted because it has become superseded by two or more records then its status.

## derived

**Scope Note:**
Indicates that the record was derived from another descriptive system.

## new

**Scope Note:**
Intial creation of an EAS record.

## revised

**Scope Note:**
Record that has been revised after initial creation.
