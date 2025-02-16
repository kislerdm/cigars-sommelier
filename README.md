# Cigars Database

The repo contains the application to extract and persist the information describing cigars from various sources:

- nobelgo.de
- cigarworld.de

## Cigar attributes

| Category       | Attribute                | Comment                                                                                                              | Example                                                                                                                                                                                                                          |                                                    nobelgo.de                                                     |                                        cigarworld.de                                         |
|:---------------|:-------------------------|:---------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------:|
| Identification | Name                     | Cigar name.                                                                                                          | No. 2                                                                                                                                                                                                                            |                                                         ✅                                                         |                                              ✅                                               |
| Identification | URL                      | Link to the data source.                                                                                             | https://www.cigarworld.de/en/zigarren/cuba/regulares/montecristo-no-2-01007_45                                                                                                                                                   |                                                         ✅                                                         |                                              ✅                                               |
| Identification | Brand                    | Manufacturer brand.                                                                                                  | Montecristo                                                                                                                                                                                                                      |                                                         ✅                                                         |                                              ✅                                               |
| Identification | Series                   | Cigar's series.                                                                                                      | -                                                                                                                                                                                                                                |                                                         ✅                                                         |                                              ✅                                               |
| Shape          | Format                   | The cigar's format.                                                                                                  | Pirámides                                                                                                                                                                                                                        |                                                         ✅                                                         |                                              ✅                                               |
| Shape          | Ring                     | The cigar's ring gauge in 64th of the inch.                                                                          | 52                                                                                                                                                                                                                               |                                                         ✅                                                         |                                              ✅                                               |
| Shape          | Diameter                 | The cigar's ring gauge in mm.                                                                                        | 20.6                                                                                                                                                                                                                             |                                                         ✅                                                         |                                              ✅                                               |
| Shape          | Length_in                | The cigar's length in inches.                                                                                        | 6.14                                                                                                                                                                                                                             |                                                         ✅                                                         |                                              ✅                                               |
| Shape          | Length_mm                | The cigar's length in mm.                                                                                            | 156                                                                                                                                                                                                                              |                                                         ✅                                                         |                                              ✅                                               |
| Manufacturing  | ManufactureOrigin        | The manufacturing country of origin.                                                                                 | Cuba                                                                                                                                                                                                                             |                                                         ✅                                                         |                                              ✅                                               |
| Manufacturing  | IsBoxpressed             | Indicates if cigar is manufactured using the box-press technology.                                                   | No                                                                                                                                                                                                                               |  ✅<br/>potentially, it may be extracted from the details page:<br/>the selector `li.product-attribute-cig_form`   |                                              ✅                                               |
| Manufacturing  | TypeOfManufacturing      | How the cigar was manufactured. Find details [here](https://www.cigarworld.de/en/zigarrenlexikon/totalmente-a-mano). | TAM                                                                                                                                                                                                                              |                                                         ❌                                                         |                                              ✅                                               |
| Manufacturing  | Maker                    | Cigar maker, or blender who created the cigar.                                                                       | AJ Fernandez                                                                                                                                                                                                                     |                                                         ✅                                                         |                                              ❌                                               |
| Manufacturing  | Construction             | Cigar's construction type.                                                                                           | Longfiller                                                                                                                                                                                                                       |                                                         ✅                                                         |                                              ❌                                               |
| Manufacturing  | IsDiscontinued           | Indicates is the cigar is no longer in making.                                                                       | No                                                                                                                                                                                                                               |                                                         ❌                                                         | ✅<br/> use the selector `div.text-danger` and search for the div text "Product discontinued" |
| Blend          | BinderOrigin             | The binder's countries of origin.                                                                                    | Cuba                                                                                                                                                                                                                             |                                                         ✅                                                         |                                              ✅                                               |
| Blend          | WrapperOrigin            | The wrapper's countries of origin.                                                                                   | Cuba                                                                                                                                                                                                                             |                                                         ✅                                                         |                                              ✅                                               |
| Blend          | FillerOrigin             | The wrapper's countries of origin.                                                                                   | Cuba                                                                                                                                                                                                                             |                                                         ✅                                                         |                                              ✅                                               |
| Blend          | IsFlavoured              | Indicates if cigar is flavoured.                                                                                     | No                                                                                                                                                                                                                               | ❌<br/>potentially, it may be extracted from the details page:<br/>the selector `li.product-attribute-cig_special` |                                              ✅                                               |
| Blend          | AromaProfileManufacturer | Array of aroma flavours according to the data source / website.                                                      | Wood, Pepper                                                                                                                                                                                                                     |                                                         ✅                                                         |                                              ❌                                               |
| Blend          | AromaProfileCommunity    | Aroma flavours with their weights from 0 to 1 according to the community.                                            | {<br/>"Wood":0.12,<br/>"Pepper":0.06,<br/>"Grass":0.06,<br/>"Fruit":0.06,<br/>"Cream":0.1,<br/>"Sweet":0.08,<br/>"Nut":0.08,<br/>"Chocolate":0.08,<br/>"Coffee":0.12,<br/>"Toast":0.08,<br/>"Leather":0.06,<br/>"Soil":0.1<br/>} |                                                         ❌                                                         |                                              ✅                                               |
| Blend          | WrapperType              | The wrapper leaf type.                                                                                               | Sun Grown                                                                                                                                                                                                                        |                                                         ✅                                                         |                                              ❌                                               |
| Blend          | AdditionalNotes          | Additional info.                                                                                                     | Barrel-aged leafs                                                                                                                                                                                                                |                                                         ✅                                                         |                                              ❌                                               |
| Experience     | SmokingDuration          | An estimation of the smoking duration in min.                                                                        | 84 min / 49 to 90 min                                                                                                                                                                                                            |                                                         ✅                                                         |                                              ✅                                               |
| Experience     | Strength                 | How strong the cigar is.                                                                                             | strong                                                                                                                                                                                                                           |                                                         ✅                                                         |                                              ❌                                               |
| Experience     | FlavourStrength          | How strong the cigar's aroma is.                                                                                     | strong                                                                                                                                                                                                                           |                                                         ✅                                                         |                                              ❌                                               |
| Purchase       | Price                    | Purchasing price in Euro per cigar.                                                                                  | 24.2                                                                                                                                                                                                                             |                                                         ✅                                                         |                                              ✅                                               |

## Knowledge graph data model

![graph-model](graph-model.png)

## TODO

- [] Add data extraction from sigarworld.de concerning the Brand
  ![img.png](img.png)