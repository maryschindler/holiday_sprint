## Data Dictionary

### .png File:
- 'downloads_schema.png', This image is a schema of this database, and provides a visual representation of the relationship between the different .csv files.


### .csv Files:
**colors.csv**
- This file contains information on LEGO colors, including a unique ID for each color, its name, and approximate RGB value, and whether it's transparent

**inventories.csv**
- This table contains information on inventories, including a unique ID, it's version and the set number.

**inventory_parts.csv**
- This table contains information part inventories, including a unique ID number, the part number, the color of the part, how many are included and whether it's a spare.

**inventory_sets.csv**
- This file contains information on what inventory is included in which sets, including the inventory ID, the set number and the quantity of that inventory that are included.

**part_categories.csv**
- This dataset includes information on the part category (what type of part it is) and a unique ID for that part category.

**parts.csv**
- This dataset includes information on lego parts, including a unique ID number, the name of the part, and what part category it's from.

**sets.csv**
- This file contains information on LEGO sets, including a unique ID number, the name of the set, the year it was released, its theme and how many parts it includes.

**themes.csv**
- This file includes information on lego themes. Each theme is given a unique ID number, a name, and (if it's part of a bigger theme) which theme it's part of.


### .csv File Descriptions:
**colors.csv**
|Column	|Column Description	|
|---	|---	|
|id	|Unique ID for this color.	|
|name	|The human-readable name of the color.	|
|rgb	|The approximate RGB color.	|
|is_trans	|Whether or not the given color is transparent/translucent.	|

**inventories.csv**
|Column	|Column Description	|
|---	|---	|
|id	|Unique ID for this inventory entry.	|
|version	|Version number.	|
|set_num	|Set number (from(sic) `sets.csv`).	|

**inventory_parts.csv**
|Column	|Column Description	|
|---	|---	|
|inventory_id	|Unique ID for the inventory this part is appearing in. This is the same as the id value in `inventories.csv`.	|
|part_num	|Unique ID for the part.	|
|color_id	|Unique ID for the color, as per `colors.csv`.	|
|quantity	|The number of copies of this part included in the set!	|
|is_spare	|Whether or not this is a spare part. Spare parts are additional parts not needed to finish the set.	|

**inventory_sets.csv**
|Column	|Column Description	|
|---	|---	|
|inventory_id	|Unique inventory ID from `inventories.csv`.	|
|set_num	|Unique set ID from `sets.csv`.	|
|quantity	|The quantity of the inventory included.	|

**part_categories.csv**
|Column	|Column Description	|
|---	|---	|
|id	|Unique ID for the part category.	|
|name	|The category of stuff the part is in.	|

**parts.csv**
|Column	|Column Description	|
|---	|---	|
|part_num	|Unique ID for the part.	|
|name	|Name of the part.	|
|part_cat_id	|Part category unique ID (from `part_categories.csv`).	|

**sets.csv**
|Column	|Column Description	|
|---	|---	|
|set_num	|Unique set ID.	|
|name	|The name of the set.	|
|year	|Year the set was published.	|
|theme_id	|Unique ID for the theme used for the set (from `themes.csv`).	|
|num_parts	|The number of parts included in the set.	|

**themes.csv**
|Column	|Column Description	|
|---	|---	|
|id	|Theme unique ID.	|
|name	|Name of the theme.	|
|parent_id	|Unique ID for the larger theme, if there is one.	|