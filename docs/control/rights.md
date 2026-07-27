---
layout: default
title: Rights Declaration
parent: Control
nav_order: 5
---

# Access and use

**Schema:**
EAS 

**Context:**
Encoding information about usage rights of the EAS instance within `<control>`. 

For describing access for using archival material itself, including copyright and permissions for reuse of archival content, see [Access and Use](/docs/description/access-use.md).

**Description:**
Information about usage rights of the EAS instance or the finding aid belongs in the `<rightsDeclaration>` element. Do not use this element for information about usage rights for the archival material itself.

`<rightsDeclaration>` is a child element of <control>. It is optional but recommended. Use it to indicate what license applies for using or re-using the content of the EAS instance. This may be a shared published license, such as Creative Commons, or a published license defined locally.

The child elements of `<rightsDeclaration>` are `<reference>`, `<shortCode>` and `<descriptiveNote>`, in that order. `<reference>` is mandatory and the other two are optional. 

Use `<reference>` to encode the name of the license statement and a URI or other machine-readable reference to it. If desired, use `<shortCode>` to provide an abbreviated name for the license statement. If desired, use `<descriptiveNote>` to provide a human-readable description of the license statement.

`<rightsDeclaration>` is a repeatable element to allow for more complex situations where more than one license applies. For instance, if a finding aid includes a biographical note (encoded in the `<biogHist>` element) written by an external expert who retains the copyright in their work, use a separate `<rightsDeclaration>` element for each license. To allow cross-referencing between the rights statement and the specific portion of the EAS instance to which it applies, include: 

- an @id attribute in `<rightsDeclaration>` to provide a unique identifier for this element, and
- a @target attribute in the highest level element of the relevant part of the EAS instance (e.g. `<biogHist>`), pointing back to that @id. 

See also the Best Practices Guide chapter on [internal references](https://saa-sdt.github.io/EAS-Best-Practices/docs/references/internal-ref.html) using the @id and @target attributes.

**Example**
A rights declaration that applies to the whole of an EAD instance:
<!-- Use codeblock below to include encoded content. You may add multiple code blocks if necessary -->
```
<control>
  <rightsDeclaration>
    <reference href="https://creativecommons.org/publicdomain/zero/1.0/">Creative Commons CC0 1.0 Universal (CC0 1.0) Public Domain Dedication</reference> 
    <shortCode>CC0 1.0</shortCode> 
    <descriptiveNote> 
      <p>All existing copyrights and related rights to this finding aid have been waived and the finding aid is under the CC0 1.0 Universal (CC0 1.0) Public Domain Dedication. This means that you can copy, modify, and distribute this finding aid, even for commercial purposes, without asking permission.</p> 
     </descriptiveNote> 
  </rightsDeclaration>
</control>
```

**Example**
A rights declaration that applies to the content of a specific `<biogHist>` element: 
<!-- Use codeblock below to include encoded content. You may add multiple code blocks if necessary -->
```
<control>
  <rightsDeclaration id="rightsstatement2" target="biog1984">
    <reference href="https://creativecommons.org/licenses/by-nc-nd/4.0/">
    Creative Commons Attribution-NonCommercial-NoDerivatives 4.0
    International</reference> 
    <shortCode>CC BY-NC-ND 4.0</shortCode> 
    <descriptiveNote> 
      <p>The biographical summary of Jenkinson's life and work was written by Dr. Joanna Doe. You may use it for non-commercial purposes only and with appropriate credit. Permission from the rights owner is required for commercial use or to distribute modified versions of the text.</p> 
    </descriptiveNote> 
  </rightsDeclaration>
</control>
```

**Example**
The reciprocal cross-reference from the `<biogHist>` element to the rights declaration:
<!-- Use codeblock below to include encoded content. You may add multiple code blocks if necessary -->
```
<archDesc>
  <biogHist id="biog1984" target="rightsstatement2">
    ...
  </biogHist>  
</archDesc>
```