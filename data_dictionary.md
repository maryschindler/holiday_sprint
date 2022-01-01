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