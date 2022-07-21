---
layout: default
title: Grouping events in a chronological list
parent: Chronological list
nav_order: 1
---

# Grouping events in a chronological list

**Schema:**
EAC-CPF

**Context:** 
Encoding two or more events and/or places within a timeline.

**Description:** 
Bundle multiple events `<event>` and/or places `<place>` within an element `<chronItemSet>` within `<chronItem>` to enter separate events occurring during a particular time period, e.g. multiple places visited in a particular timeframe understood better in a group than as separate occurrences. The example below contains itinerary data for a scientific expedition grouping multiple locations under distinct travel periods. Can be used to encode multiple event-based lists within a larger timeline.

Possible combinations include multiple events, a single event associated with multiple locations, multiple events associated with a single location, or multiple events associated with multiple locations. `<chronItemSet>` may be repeated within `<chronItem>` when necessary to associate multiple instances of such combinations with the date or dates recorded within `<chronItem>`.

A number of attributes are available to qualify data such as language, source references, maintenance event references (to indicate the occurrence and agent responsible for the data), language encoding, and locally defined conventions.

`<chronItem>` and `<chronItemSet>` are subelements of `<chronList>`, `<bioghist>`, while `<description>`, `<event>`, `<place>` and date elements are subelements of `<chronItem>` and `<chronItemSet>`. Refer to `<place>` for attributes.

**Example**
```xml
<chronList>
  <chronItem>
    <date standardDate="1909-08-31">August 31, 1909</date>
    <event>The party departs Naples, Italy via SS Adolph Woermann, where they are introduced to Sir Percy Girouard, the new British East Africa governor</event>
    <place valueURI="http://vocab.getty.edu/tgn/7004474">Naples</placeEntry>
  </chronItem>
  <chronItem>
    <date standardDate="1909-09">September 1909</date>
      <chronItemSet>
        <event>Arrive in Mombasa, Sir Percy Girouard invites expedition party to travel by private rail to Nairobi</event>
        <place valueURI="http://vocab.getty.edu/tgn/7001115">Mombasa</place>
        <event>In Nairobi the party reconnects with old acquaintances and purchases supplies for the journey. /event>
        <place valueURI ="http://vocab.getty.edu/tgn/7001116">Nairobi</place>
      </chronItemSet>
  </chronItem>
  <chronItem>
    <date standardDate="1909-10">October 1909</date>
      <chronItemSet maintenanceEventReference="maintenancevent1" sourceReference="source1">
        <event>Spent two weeks hunting rhino and lion, in the Lower Tana River Valley, Delia Akeley procures a small monkey and names her J.T. Jr.</event>
        <place valueURI ="http://vocab.getty.edu/tgn/7593796">Tana River</place>
        <event>Hunting elephants in Mt. Kenya</event>
        <place valueURI ="http://vocab.getty.edu/tgn/1105240">Kirinyaga</place>
    </chronItemSet>
  </chronItem> 
</chronList>
```

_Field work and expeditions in the early 20th century often involved harmful acts inflicted upon animals and communities for scientific research. While these practices are not conducted on large mammals today, historical events below are presented as they occurred or appear in evidentiary documentation._

