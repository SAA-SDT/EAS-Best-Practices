---
layout: default
title: agentType
parent: EAS Value Lists
nav_order: 1
---

# agentType

**Scope Note:**
To identify different types of agents who have created, managed, modified, published, or otherwise engaged with the archival materials being described, are mentioned in the materials, or have played a role in creating, modifying, and maintaining the EAS instance in question. Resources consulted for value terms and scope notes include:

- ISAAR(CPF) International Standard Archival Authority Record for Corporate Bodies, Persons and Families, 2nd Edition: [https://www.ica.org/app/uploads/2023/12/CBPS_Guidelines_ISAAR_Second-edition_EN.pdf](https://www.ica.org/app/uploads/2023/12/CBPS_Guidelines_ISAAR_Second-edition_EN.pdf)
- Records in Contexts Conceptual Model (RiC-CM), Version 1.0: [https://www.ica.org/app/uploads/2024/01/ric-cm-1.0_0.pdf] (https://www.ica.org/app/uploads/2024/01/ric-cm-1.0_0.pdf)
- Tag Library for the Encoded Archival Context - Corporate Bodies, Persons, and Families (EAC-CPF) 2.0.1: [https://eac.staatsbibliothek-berlin.de/schema/v2/eac.html](https://eac.staatsbibliothek-berlin.de/schema/v2/eac.html)

`@agentType` is an attribute used to specify the type of agent in `<agent>`. Accepted values for `@agentType` are listed below with scope notes. 

**Example**
```
<agent agentType="person">
  <label>Marie Curie</label>
  <role>Creator</role>
</agent>
```
___

## corporateBody
**Scope Note:**
An organization or group of persons that is identified by a particular name and that
acts, or may act, as an entity. Also includes an individual acting in a corporate capacity. 

## family 
**Scope Note:** 
... 

## group 
**Scope Note:** 
Two or more agents that act together as an agent. Traditionally, corporate bodies and families are recognized kinds of groups, but it may be useful, within some contexts, to define additional kinds of groups. For example an "electorate", i.e. all of the voters in a given election, or other identifiable collective movements that are not formally corporate bodies, but that do perform activities governed by shared values or commitments. 

## human 
**Scope Note:** 
... 

## mechanism
**Scope Note:** 
... 

## person 
**Scope Note:** 
An individual human being. Most commonly, a human being (biological person) has a single socially constructed identity or persona. Less common though not rare, one or more personae in addition to the original persona may be associated with the human being over the course of their lifetime. Less common is when two or more persons collaborate to create a shared persona, constituting a kind of group. 

## position 
**Scope Note:** 
... 

## unknown 
**Scope Note:** 
...  
