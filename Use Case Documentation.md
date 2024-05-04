# Description of use case

## Name of use case
|ID|Industry|Name of use case|
|--|--------|----------------|
|  |Building|Lighting fixture selection|

## Scope and objective of use case

### Scope
This use case covers the implementation of data templates in the process of selection of a light fixture from the Inception stage to handover stage.

### Objectives
+ Ensure circularity. Being able to repurpose objects based on key properties.
+ Interoperability across the value chain.
+ Improved lighting simulation.

### Business need 
Provide stakeholders with a framework to optimize selection of products based on function.

### Short description
This use case delineates a systematic approach for the selection of appropriate lighting fixtures designed to meet specific spatial lighting requirements. It encompasses the inception, design brief and design phases, offering stakeholders the capability to choose products based on their functionality while also satisfying predefined key requirements. The employment of standardized data templates is intended to have machine-readable information and preserve data integrity throughout the entire value chain. Furthermore, the methodologies and data structures outlined in this use case are scalable to subsequent stages of operation and maintenance. 

## Use case type
### Type of use case 
Compliance use case

## Relationship with other use cases
-------
## References
|#  |Reference              |Impact              |Type          |Published by        |
|---|-----------------------|--------------------|--------------|--------------------|
|1  |SS-EN ISO 12006-2:2020 Strukturering av information om byggnadsverk – Del 2: Ramverk för klassificering (av information) (ISO 12006‑2:2015)| Grund för klassificering av objekt inom byggindustrin.|Standard|Svenska Instituet för Standard|
|2  |SS-EN ISO 12006-3:2022 Strukturering av information om byggnadsverk –Del 3: Ramverk för objektorienterad information (ISO 12006-3:2022) | Grund för utveckling av data lexikon som används i standardiserade informationsmodeller.| Standard|Svenska Instituet för Standard|
|3  |SS-EN 17412-1:2020 Byggnadsinformationsmodellering – Nivåer för informationsbehov – Begrepp och principer| Koncept och principer för att definiera informationsbehovsnivån och informationsleveranser som ingår i informationsutbytesprocesserna under livscykeln för byggda tillgångar vid användning av bygginformationsmodellering (BIM)|Standard|Svenska Instituet för Standard|
|4  |ISO/TS 7127:2023(E) Light and lighting — Building information modelling properties for lighting — Lighting systems | Standardiserade egenskaper för domänen | Standard|Svenska Instituet för Standard|

# Purpose of the use case
## Narrative of the use case
### Long description
The brief, with focus on space function, is developed by the client, and documented in a machine-readable format using standardized properties defined in a data dictionary. These should include both lighting technical requirements and guidelines based on references to standards and planning guides. In collaboration with the architect, the desired room experience is also described. In this functional test an office space is used as a case study.
These requirements are translated by the lighting designer (or another designer) into a technical solution, for example, by using lighting simulations and analysis as well as providing other technical documentation. This technical solution includes descriptions of control, lighting principles, ambient light, and products, such as light fixtures. The products are described by the product supplier using standardized properties defined in a data dictionary. This information is accessed through a URI. The light fixture, Notor 65 Beta opti is used as a case study based on what was developed in the Map4Light project.
The products chosen by the lighting design can also be seen as a basis for requirements. This is done by defining certain properties as critical or key properties. The contractor uses these requirements (key properties) to propose a final product selection. If the final product selection differs from the lighting designer's choice, a new verification is carried out, for example, through light simulation, to ensure that the finally selected products meet the requirements described in the program. This verification occurs in consultation with the client.
An information structure with requirements and final product selections is handed over to the client at the handover of the building. 

## Impacts and benefits
|#|Impact/Benefit|Further information|
|-|--------------|-------------------|
|1|Standardisation of information flow and exchange throughout a project lifecycle.| |
|2|This can lead to improved simulation results as properties used will be directly from manufacturers| |

## Actors
|#  |Party (Nationella Riktlinjer)| Party (OmniClass Table 33)|Task/role          |Further Information|
|---|-----------------------|--------------------|--------------|---------------------|
|1  |Beställare  |Facility Owner|Initiate the process from actioning investigations and producing an RFP| |
|2  |Arkitekt	   |Architect |Develop 3D model and place requirements on the space	| Authoring of 3D model, Set spatial lighting requirements|
|3  |Belysning och ljusdesign	| Lighting design	| Carry out light simulations to obtain suitable product and get key properties| |
|4  |    |Manufacturing services |	Provide a database of products| |
|5  |El-entrenprenör	| Medium voltage electrical contracting	| Select, install and handover product | |

## Objective of the information exchange
The objective of the information exchanges is to have in the end an Asset Information Model (AIM) of a light fixture along with all dependent objects and properties in machine readable format. This should be sufficient to ensure that the spatial lighting functional requirements are satisfied along the life cycle of the product.

## Assumptions
+ In defining these data requirements, it has been assumed that the product database may contain data from different manufactures.

# Information exchange workflow
## Description of the steps and tasks involved in the exchange of information.

|#	|Task description	|Author|
|---|-----------------|------|
|1	|The Facility owner is to initiate the process with the Identification of need and provide a Room functional program (RFP) in a machine-readable format.	|The Facility owner (or a representative)|
|2	|Issue Exchange information requirements (EIR), er_01, for the purpose of visualization. |	Architect|
|3	|Deliver information in response to er_01	|The Facility owner (or a representative)|
|4	|The Architect uses the RFP and other information from the inception stage to develop a 3D BIM and place lighting requirements in accordance with SS-EN 12464-1	|Architect|
|5	|Issue EIR (er_02) for the purpose of lighting design and simulation	|Lighting design|
|6	|Deliver information in response to er_02	|Architect|
|7	|Run first simulation loop to obtain a suitable light fixture based on the information deliveries from the Architect and product database from the Manufacturer.  	|Lighting design|
|8	|Revert to the Architect if certain elements need to be modified and go to step 7, otherwise go to step 9	|Lighting design|
|9	|Develop light fixture requirements based on key properties from simulation	|Lighting design|
|10	|Select a suitable light fixture satisfying the key properties in the light fixture requirements. The contractor accesses the product database of a manufacturer to make this selection.	|Medium voltage electrical contracting|
|11	|Perform a second simulation loop with the product selected by the contractor. 	|Lighting design|
|12	|If the product satisfies the requirements on the space, it is approved and proceed to step 13, otherwise go to step 10.	|Architect| 
|13	|Purchase and install the product and handover product information to the Facility owner	|Medium voltage electrical contracting|

## Diagrams and process map
<img src="https://github.com/sosabaa/Datamallar/assets/73257793/3c04da1f-35db-4b9e-b107-6b9e264d3ae8" alt="Process Diagram"/>


# Exchange requirements
## General description of the information to be exchanged

## Room
|Component	|Rooms inside a building or structure|
|-----------|------------------------------------|
|EIR ID	|er_01|
|Object	|IfcSpace|
|Object URI|https://identifier.buildingsmart.org/uri/buildingsmart/ifc/4.3/class/IfcSpaceINTERNAL|
|Purpose|  10 Visualisering| 
|Milestone| 1 Programskede|
|Detail level| Functional|
|Actor| Client|
|**Alphanumeric information:**|   |
|IFC Object Name |	Room number. At the building permit stage, the room number is not mandatory.|
|IFC Object Description |	Room name. The room name is mandatory.|
|IFC PredefinedType	| Internal|
|**IFC Properties:**|  |
|---------------|-------------------|
|	Data content needs |	Type of the room|
|	Limitations	|-|
|	Propertyset|	Pset_SpaceOccupancyRequirements|
|	Property	|OccupancyType|
| URI/GUID|https://identifier.buildingsmart.org/uri/buildingsmart/ifc/4.3/class/IfcSpaceINTERNAL/prop/Pset_SpaceOccupancyRequirements/OccupancyType|
|	Allowed values	| According to national building code.|
| Key property    |The value must be TRUE if the property is a key property for the object. Otherwise, the value is FALSE or empty.|
|-----------------|-------------------|
|	Data content needs  |	Capacity of persons| 
|	Limitations	|- The number of persons is only given for the premises for which it is needed (e.g., meeting rooms); - The value is the maximum number of people in the room.|
|	Propertyset	|Pset_SpaceOccupancyRequirements|
|	Property	| OccupancyNumber|
| URI/GUID|https://identifier.buildingsmart.org/uri/buildingsmart/ifc/4.3/class/IfcSpaceINTERNAL/prop/Pset_SpaceOccupancyRequirements/OccupancyNumber|
|	Allowed values |	Maximum number of persons in the room (total)|
| Key property    |The value must be TRUE if the property is a key property for the object. Otherwise, the value is FALSE or empty.|
|-----------------|-------------------|
|	Data content needs  |	Capacity of room| 
|	Limitations	|- |
|	Propertyset	|Pset_SpaceCommon|
|	Property	| NetPlannedArea|
| URI/GUID|https://identifier.buildingsmart.org/uri/buildingsmart/ifc/4.3/class/IfcSpaceINTERNAL/prop/Pset_SpaceCommon/NetPlannedArea|
|	Allowed values |	Square area|
| Key property    |The value must be TRUE if the property is a key property for the object. Otherwise, the value is FALSE or empty.|
|-----------------|-------------------|
|	Data content needs	|Accessibility|
|	Limitations	|-|
|	Propertyset |	Pset_SpaceCommon|
|	Property	|HandicapAccessible|
|	Allowed values	| The value must be TRUE if the space is intended to be accessible or serves access to an accessible space. Otherwise, the value is FALSE or empty.|
| URI/GUID|https://identifier.buildingsmart.org/uri/buildingsmart/ifc/4.3/class/IfcSpaceINTERNAL/prop/Pset_SpaceCommon/HandicapAccessible|
| Key property    |The value must be TRUE if the property is a key property for the object. Otherwise, the value is FALSE or empty.|
|**Documentation:** |  |
|	Document	| - |


## Light fixture
|Component	|Light Fixture in internal space|
|-----------|------------------------------------|
|EIR ID	|er_04|
|Object	|IfcLightFixture|
|Object URI|https://identifier.buildingsmart.org/uri/buildingsmart/ifc/4.3/class/IfcLightFixture|
|Purpose|  40 Ekonomi| 
|Milestone| 2 Projekteringsskede|
|Detail level| Component|
|Actor| Manufacturer|
|**Alphanumeric information:**|   |
|IFC Object Name |	Light Fixture name.|
|IFC Object Description |	-|
|IFC PredefinedType	| -|
|**ISO/TS 7127 Properties:**|  |
|---------------|-------------------|
|	Data content needs |	Length of light fixture|
|	Limitations	|-|
|	Propertyset|	Mechanical_Properties|
|	Property	|overall_length|
| URI/GUID|1uJglYpRnFpQ4tStHaR2Pf|
|	Allowed values	| -|
| Key property    |The value must be TRUE if the property is a key property for the object. Otherwise, the value is FALSE or empty.|
|-----------------|-------------------|
|	Data content needs |	Height of light fixture|
|	Limitations	|-|
|	Propertyset|	Mechanical_Properties|
|	Property	|overall_height|
| URI/GUID|19Z9XKYDT4p8HR0ZbD$wO_|
|	Allowed values	| -|
| Key property    |The value must be TRUE if the property is a key property for the object. Otherwise, the value is FALSE or empty.|
|-----------------|-------------------|
|	Data content needs |	Manufacturer details|
|	Limitations	|-|
|	Propertyset|	Marketing_Properties|
|	Property	|Manufacturer|
| URI/GUID|3gmbhSjFD4JOPQZ7_I$HzY|
|	Allowed values	| -|
| Key property    |The value must be TRUE if the property is a key property for the object. Otherwise, the value is FALSE or empty.|
|-----------------|-------------------|
|	Data content needs |	Product identifiction|
|	Limitations	|-|
|	Propertyset|	Marketing_Properties|
|	Property	|item_number|
| URI/GUID|29UfpgwX5Eyu$KCZIxfJZy|
|	Allowed values	| -|
| Key property    |The value must be TRUE if the property is a key property for the object. Otherwise, the value is FALSE or empty.|
|**Documentation:** |  |
|	Document	| - |
