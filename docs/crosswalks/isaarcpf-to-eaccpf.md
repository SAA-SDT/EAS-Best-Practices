---
layout: default
title: ISAAR(CPF) to EAC-CPF
parent: Crosswalks
nav_order: 1
---

# ISAAR (CPF) to EAC-CPF
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 5.1 Identity area

| ISAAR (CPF)                                               | EAC-CPF `<cpfDescription>` `<identity>`       |
|:----------------------------------------------------------|:----------------------------------------------|
| 5.1.1 Type of entity                                      | `<entityType @value>`                         |
| 5.1.2 Authorized form(s) of name                          | `<nameEntry @status="authorized">`            |
| 5.1.3 Parallel forms of name                              | `<nameEntrySet @localType="parallel">`        |
| 5.1.4 Standardized forms of name according to other rules | `<nameEntry @conventionDeclarationReference>` |
| 5.1.5 Other forms of name                                 | `<nameEntry>`                                 |
| 5.1.6 Identifiers for corporate bodies                    | `<identityId>`                                |

## 5.2 Description area

| ISAAR (CPF) | EAC-CPF `<cpfDescription>` `<description>` |
|-----|-----|
| 5.2.1	Dates of existence | `<existDates>` |
| 5.2.2	History | `<biogHist>` |
| 5.2.3 Places | `<places>` |
| 5.2.4 Legal status | `<legalStatuses>` |
| 5.2.5 Functions, occupations and activities | `<functions>` & `<occupations>` |
| 5.2.6 Mandates/Sources of authority | `<mandates>` |
| 5.2.7 Internal structures/Genealogy  | `<structureOrGenealogy>` |
| 5.2.8 General context | `<generalContext>` |

## 5.3 Relationships area

| ISAAR (CPF) | EAC-CPF `<cpfDescription>` `<relations>` `<relation>` |
|-----|-----|
| 5.3.1	Identifiers of related corporate bodies, persons or families | `<targetEntity @valueURI>` |
| 5.3.1	Names of related corporate bodies, persons or families | `<part>` |
| 5.3.2 Category of relationship | `<relationType>` |
| 5.3.3 Description of relationship | `<targetRole>` & `<descriptiveNote>` |
| 5.3.4 Dates of the relationship | `<date>` or `<dateRange>` or `<dateSet>` |

## 5.4 Control area

| ISAAR (CPF) | EAC-CPF `<control>` |
|-----|-----|
| 5.4.1	Authority record identifier | `<recordId>` |
| 5.4.2	Institution identifiers | `<maintenanceAgency>`	`<agencyCode>` |
| 5.4.3 Rules and/or conventions | `<conventionDeclaration>` |
| 5.4.4 Status | `@maintenanceStatus` |
| 5.4.5 Level of detail | `@detailLevel` |
| 5.4.6 Dates of creation, revision or deletion | `<maintenanceHistory>`	`<maintenanceEvent>` |
| 5.4.7 Language(s) and script(s) | `<languageDeclaration>` |
| 5.4.8 Sources | `<sources>` |
| 5.4.9 Maintenance notes | `<maintenanceHistory>`	`<maintenanceEvent>` |

## 6.1 Relating corporate bodies, persons and families to archival materials and other resources

| ISAAR (CPF) | EAC-CPF `<cpfDescription>` `<relations>` `<relation>` |
|-----|-----|
| 6.1	Identifiers and titles of related resources | `<targetEntity @valueURI>` |
| 6.2	Types of related resources | `<targetEntity @targetType>` |
| 6.3 Nature of relationships | `<targetRole>` |
| 6.4 Dates of related resources and/or relationships | `<date>` or `<dateRange>` or `<dateSet>` |
