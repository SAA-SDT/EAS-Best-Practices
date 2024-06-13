---
layout: default
title: contactLineType
parent: Value lists
nav_order: 3
---

# contactLineType

**Scope Note:**
To identify the different parts of an electronic address and details necessary to contact and/or communicate with someone. [^1].

[^1]: Encoded Archival Guide (EAG): [http://www.apex-project.eu/index.php/en/outcomes/standards/eag-2012/tag-library] (http://www.apex-project.eu/index.php/en/outcomes/standards/eag-2012/tag-library)

**EAC-CPF 2.0:**
`@contactLineType` is used in `<contactLine>` with the following values: *directions, email, fax, homepage, mobileNumber, phoneNumber.*

**EAD4:**
`@contactLineType` is used in `<control>` with the following values: *EASList, otherContactLineTypeEncoding.* When choosing *EASList* add another `@contactLineType` with the following values: *directions, email, fax, homepage, mobileNumber, phoneNumber.* When choosing *otherContactLineTypeEncoding* specify the source and code in `<conventionDeclaration>`.

## directions
**Scope Note:**
Directions to get to a geographic location or feature, eg by for public transport. [^2]

[^2]: In extension of ISDIAH chapter 5.2.1 Location and address(es), [https://www.ica.org/app/uploads/2023/12/CBPS_2008_Guidelines_ISDIAH_First-edition_EN.pdf] (https://www.ica.org/app/uploads/2023/12/CBPS_2008_Guidelines_ISDIAH_First-edition_EN.pdf)
