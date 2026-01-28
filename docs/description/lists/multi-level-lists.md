---
layout: default
title: Multi-level lists
parent: Lists as part of narrative description
nav_order: 2
---

# Multi-level lists

**Schema:** 
EAC-CPF 2.0

**Context:** 
Using multi-level lists in the context of narrative description to convey more complex structures.

**Description:** 
Next to allowing for the use of repeated `<item>` elements to create simple lists, the element `<list>` can also be used recursively, i.e. `<list>` can also include another `<list>`. Such multi-level lists can be of help when encoding more complex structures, e.g. a table of content of a person’s main publication in `<biogHist>` or in `<generalContext>`, or a family tree or an organizational chart in the context of `<structureOrGenealogy>`. Depending on the use case, there might be `<item>` and `<list>` elements next to each other within `<list>`, e.g. when representing the person being described as an `<item>` and including their children as `<item>`-s within a nested `<list>` on the same level. Especially with multi-level lists, the use of the optional element `<head>` would be recommended to indicate the relation of each nested `<list>` to their parent `<list>` or to the main `<list>` overall. 

**Examples**
```xml
<cpfDescription>
        <identity>
            <entityType value="person"/>
            <nameEntry>
                <part localType="firstname">Johan Sebastian</part>
                <part localType="lastname">Bach</part>
            </nameEntry>
        </identity>
        <description>
            <!-- [...] -->
            <structureOrGenealogy>
                <!-- [...] -->
                <list listType="unordered">
                    <head>Children of Johann Sebastian Bach and Maria Barbara Bach</head>
                    <item>Catharina Dorothea Bach</item>
                    <item>Wilhelm Friedemann Bach</item>
                    <list>
                        <head>Children of Wilhelm Friedemann Bach</head>
                        <item>Friederica Sophia Bach</item>
                        <item>Two sons who did not live past infancy</item>
                    </list>
                    <item>Carl Philipp Emanuel Bach</item>
                    <list>
                        <head>Children of Carl Philipp Emanual Bach</head>
                        <item>Johann Adam Bach</item>
                        <item>Anna Carolina Philippina Bach</item>
                        <item>Johann Sebastian Bach ("the Younger")</item>
                        <item>Other children who did not live to adulthood</item>
                    </list>
                        <item>Johann Gottfried Bernhard Bach</item>
                        <item>Three more children who did not live to their first birthday</item>
                    </list>
                <list listType="unordered">
                    <head>Children of Johann Sebastian Bach and Anna Magdalena Wilcken</head>
                    <item>Gottfried Heinrich Bach</item>
                    <item>Johann Christoph Friedrich Bach</item>
                    <list>
                        <head>Children of Johann Christoph Friedrich Bach</head>
                        <item>Anna Philippiana Friederica Bach</item>
                        <item>Wilhelm Friedrich Ernst Bach</item>
                        <list>
                            <head>Children of Wilhelm Friedrich Ernst Bach</head>
                            <item>Carolina Auguste Wilhelmine Bach</item>
                            <item>Juliane Friederica Bach</item>
                        </list>
                        <item>Christine Luise Bach</item>
                    </list>
                    <item>Johann Christian Bach</item>
                    <item>Elisabeth Juliane Friederica Bach</item>
                    <list>
                        <head>Children of Elisabeth Juliane Friederica Bach</head>
                        <item>Johann Sebastian Altnickol</item>
                    </list>
                    <item>Johanna Carolina Bach</item>
                    <item>Regina Susanna Bach</item>
                    <item>Six more children who did not live to adulthood</item>
                </list>
            </structureOrGenealogy>
        </description>
</cpfDescription>
```
```xml
<cpfDescription>
        <identity>
            <entityType value="person"/>
            <nameEntry>
                <part localType="firstname">Charles Robert</part>
                <part localType="lastname">Darwin</part>
            </nameEntry>
        </identity>
        <description>
            <!-- [...] -->
            <generalContext>
                <!-- [...] -->
                <list listType="unordered">
                    <head>The Origins of Species by Means of Natural Selection or The Preservation of 
                    Favoured Races in the Struggle of Life, 6th edition, with additions and corrections, 1873
                    </head>
                    <item>Additions and corrections, to the sixth edition</item>
                    <item>Historical sketch</item>
                    <item>Introduction</item>
                    <item>Chapter I - Variation under Domestication</item>
                    <list>
                        <item>Causes of Variability</item>
                        <item>Effects of Habit and the use or disuse of Parts</item>
                        <item>Correlated Variation</item>
                        <item>Inheritance</item>
                        <item>Character of Domestic Varieties</item>
                        <item>Difficulty of distinguishing between Varieties and Species</item>
                        <item>Origin of Domestic Varieties from one or more Specie</item>
                        <item>Domestic Pigeons, their Differences and Origin</item>
                        <item>Principles of Selection, anciently followed, their Effects</item>
                        <item>Methodical and Unconscious Selection</item>
                        <item>Unknown Origin of our Domestic Productions</item>
                        <item>Circumstances favourable to Man's power of Selection</item>
                    </list>
                    <item>Chapter II - Variation under Nature</item>
                    <list>
                        <!-- [...] -->
                    </list>
                    <item>Chapter III - Struggle for Existence</item>
                    <list>
                        <!-- [...] -->
                    </list>
                    <!-- [...] -->
                    <item>Chapter XV - Recapitulation and Conclusion</item>
                    <list>
                        <!-- [...] -->
                    </list>
                    <item>Glossary of Scientific Terms</item>
                    <item>Index</item>
                </list>
            </generalContext>
        </description>
</cpfDescription>
```
