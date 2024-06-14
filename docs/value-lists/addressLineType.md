---
layout: default
title: addressLineType
parent: EAS Value Lists
nav_order: 1
---

# addressLineType

**Scope Note:**
To identify the different parts of a physical address, e.g., for public access or to contact and/or communicate with someone by postal services. Resources consulted for value terms and scope notes include:

- Encoded Archival Guide (EAG): [http://www.apex-project.eu/index.php/en/outcomes/standards/eag-2012/tag-library](http://www.apex-project.eu/index.php/en/outcomes/standards/eag-2012/tag-library)
- ISDIAH chapter 5.2.1 Location and address(es), [https://www.ica.org/app/uploads/2023/12/CBPS_2008_Guidelines_ISDIAH_First-edition_EN.pdf](https://www.ica.org/app/uploads/2023/12/CBPS_2008_Guidelines_ISDIAH_First-edition_EN.pdf) 

`@addressLineType` is an attribute used to specify the type of address in `<addressLine>`. Accepted values for `@addressLineType` are listed below with scope notes. 

**Example**
```xml
<addressLine addressLineType="postalCode">10024</addressLine>
<addressLine addressLineType="country">United States</country>
```
___

## county
**Scope Note:**
Second-level administrative division where a geographic location or feature is located; in a specific national context, this could be a canton, a commune, a county, a department, a district, a prefecture, a province, a subprefecture, etc.; note that a term used for a second-level administrative division in one country might be used for a first-level administrative division in another country.

## country 
**Scope Note:** 
Country where a geographic location or feature is located. 

## district 
**Scope Note:** 
Area of a bigger city or town where a geographic location or feature is located. 

## municipality 
**Scope Note:** 
City, town, or village where a geographic location or feature is located. 

## postBox 
**Scope Note:** 
Post office box (postal box) number as part of the physical or postal address of a geographic location of feature. 

## postalCode 
**Scope Note:** 
Postal code (ZIP code) as part of the physical or postal address of a geographic location of feature. 

## region 
**Scope Note:** 
First-order administrative division where a geographic location or feature is located; in a specific national context, this could be an autonomous or administrative region, a prefecture, a province, a state etc.; note that a term used for a first-level administrative division in one country might be used for a second-level administrative division in another country.  

## street 
**Scope Note:** 
Street name and house number and/or house name as part of the physical or postal address of a geographic location or feature.  
