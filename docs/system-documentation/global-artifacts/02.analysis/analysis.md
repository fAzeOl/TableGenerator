# OO Analysis

The construction process of the domain model is based on the client specifications, especially the nouns (for _concepts_) and verbs (for _relations_) used.

## Rationale to identify domain conceptual classes
Domain conceptual classes where identified by making a list of candidate conceptual classes inspired by the list of categories suggested in the book "Applying UML and Patterns: An Introduction to Object-Oriented Analysis and Design and Iterative Development".


### _Conceptual Class Category List_

**Business Transactions**

- Transaction
- Routes

---

**Transaction Line Items**

- Cargo

---

**Product/Service related to a Transaction or Transaction Line Item**

- Passengers
- Mail
- New Product
- Final Product
- Resources

---

**Transaction Records**

*

---  

**Roles of People or Organizations**

- Editor
- Player

---

**Places**

- Scenario
- City
- Industry

---

**Noteworthy Events**

- Event

---

**Physical Objects**

- RailwayLine
- Train
- Locomotive
    - LocomotiveType
        - Diesel
        - Steam
        - Electric
- Carriage
- Station
    - StationType
        - Depot
        - Station_
        - Terminal
- StationUpgrade
- RailwayLineType
- Track
- ElectrifiedTrack
- Port

---

**Descriptions of Things**

*

---

**Catalogs**

*

---

**Containers**

- Scenario
- Railway Network

---

**Elements of Containers**

- Historical Restrictions
- Time Restrictions
- Technological Restrictions

---

**Organizations**

- Railroad Tycoon

---

**Other External/Collaborating Systems**

*

---

**Records of finance, work, contracts, legal matters**

*

---

**Financial Instruments**

- Budget
- Demand
- Supply

---

**Documents mentioned/used to perform some work/**

*

---



## Rationale to identify associations between conceptual classes

An association is a relationship between instances of objects that indicates a relevant connection and that is worth of remembering, or it is derivable from the List of Common Associations:

- **_A_** is physically or logically part of **_B_**
- **_A_** is physically or logically contained in/on **_B_**
- **_A_** is a description for **_B_**
- **_A_** known/logged/recorded/reported/captured in **_B_**
- **_A_** uses or manages or owns **_B_**
- **_A_** is related with a transaction (item) of **_B_**
- etc.


| Concept (A)           |  Association   |           Concept (B) |
|-----------------------|:--------------:|----------------------:|
| User                  |      has       |                Player |
| User                  |      has       |                Editor |
| Railroad Tycoon II    |    contains    |                  User |
| Editor                |    creates     |              Scenario |
| Editor                |    creates     |                   Map |
| Scenario              |      has       |           Restriction |
| Scenario              |    applied     |                   Map |
| Map                   |      has       |              Location |
| Location              |    includes    |               Station |
| Location              |    includes    |              Industry |
| Location              |    includes    |                  City |
| City                  |      has       |            HouseBlock |
| HouseBlock            |    transact    |            Passengers |
| HouseBlock            |    transact    |                  Mail |
| Industry              |     can be     | PrimarySectorIndustry |
| PrimarySectorIndustry |   generates    |             Resources |
| Resources             |   converted    |                 Cargo |
| Cargo                 |  transported   |               Station |
| Cargo                 |  transported   |  TransformingIndustry |
| Cargo                 |  transported   |         MixedIndustry |
| Cargo                 |      has       |                  Mail |
| Cargo                 |      has       |          FinalProduct |
| Cargo                 |      has       |            Passengers |
| Cargo                 |      has       |            NewProduct |
| Station               |     serves     |                  City |
| Industry              |     can be     |  TransformingIndustry |
| TransformingIndustry  |    produces    |            NewProduct |
| TransformingIndustry  |    produces    |          FinalProduct |
| Industry              |     can be     |         MixedIndustry |
| MixedIndustry         |      has       |                  Port |
| Port                  |     import     |                 Cargo |
| Port                  |     export     |                 Cargo |
| Player                |   chooses a    |              Scenario |
| Player                |     builds     |        RailwayNetwork |
| Player                |    defines     |                 Route |
| Route                 |      uses      |        RailwayNetwork |
| RailwayNetwork        |      has       |           RailwayLine |
| RailwayNetwork        |      has       |               Station |
| RailwayNetwork        |      has       |                 Train |
| Station               |      has       |           StationType |
| StationType           |    inherits    |                 Depot |
| StationType           |    inherits    |              Station_ |
| StationType           |    inherits    |              Terminal |
| Station               |     serves     |              Industry |
| Station               |      has       |        StationUpgrade |
| Train                 |   circulates   |           RailwayLine |
| Train                 |      has       |            Locomotive |
| Train                 |      has       |              Carriage |
| RailwayLine           |      has       |       RailwayLineType |
| RailwayLineType       |     can be     |      ElectrifiedTrack |
| RailwayLineType       |     can be     |                 Track |
| Locomotive            | is composed by |        LocomotiveType |
| LocomotiveType        |     can be     |                Diesel |
| LocomotiveType        |     can be     |                 Steam |
| LocomotiveType        |     can be     |              Electric |
| Track                 |   circulates   |                Diesel |
| Track                 |   circulates   |                 Steam |
| ElectrifiedTrack      |   circulates   |                Diesel |
| ElectrifiedTrack      |   circulates   |                 Steam |
| ElectrifiedTrack      |   circulates   |              Electric |
| Player                |      runs      |             Simulator |
| Simulator             |    manages     |                 Event |
| Transaction           |   generates    |                 Event |
| Event                 |    updates     |                Budget |
| Station               |   generates    |           Transaction |
| Scenario              |   applies to   |             Simulator |
| Restriction           |    affects     |                 Train |
| Restriction           |    affects     |        LocomotiveType |
| Restriction           |    affects     |              Industry |
| Restriction           |    affects     |        StationUpgrade |
| Restriction           |    affects     |       RailwayLineType |
| Restriction           |    affects     |                  City |
| City                  |      has       |                Demand |
| City                  |      has       |                Supply |
| Industry              |      has       |                Demand |
| Industry              |      has       |                Supply |
| Scenario              |   generates    |                 Event |
| Industry              |   generates    |                 Event |
| City                  |   generates    |                 Event |
| Event                 |   influence    |                Demand |
| Event                 |   influence    |                Supply |
| Event                 |    generate    |                 Cargo |


## Domain Model

**Do NOT forget to identify concept atributes too.**

**Insert below the Domain Model Diagram in a SVG format**

![Domain Model](svg/DM.svg)