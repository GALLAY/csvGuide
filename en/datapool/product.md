# General

The Products area shows a list with all products/parents of the active data source stored in the data pool.
Existing product data in the data pool is a prerequisite for using a CSV or API interface.

If data sets have already been imported or created, you will see a list of your products here.
Different sorting options are available via the small button with the two arrows
(ascending/descending) to the right of the search.

Assigning products to internal categories is an important prerequisite for exporting your data
(incl. store categories) in the export section.

***
# Products

- **All products**<br>All products from this data source will be displayed to you.

- **Products with inventory**<br>Only products with available inventory will be displayed.

- **Products without inventory**<br>Products that do not have any inventory will be displayed.

- **Not Available**<br>Here, you will find an overview of products that were not included in the last product update.
    This allows you to quickly sort out older or discontinued products.    

> Example: Your wholesaler only provides data in their CSV files for items they have in stock.
  Items that are out of stock or discontinued at the wholesaler will not appear in the file.
  Over time, this can result in accumulating product numbers in the system that have not been modified
  for quite some time and have not received any inventory updates (despite regular imports).
  Using this tab, such products can be quickly identified and removed from the system if needed.

***
# Parents

Here is an overview of the existing main articles of a variation.

> Variations can be, for example, necklaces in different lengths: 1010-42, 1010-45, 1010-50 (cm),
  or shirts in various colors: 1020-red, 1020-blue, and 1020-green. There are several ways
  to represent variant items in the system. Your preference will depend on the structure
  of your datasets, your approach, or even the platform where your data will be imported.

### Differentiation of the parent types

#### Parents

Parents can be stored as independent records in the data pool: `Create a new parent`.
Any products can be associated with such parents as variant items. Once parents are created,
you can delete them at any time. In this case, only the parent records will be deleted,
not the products associated with them.

![Overview parents](https://data.csv4you.com/media/image/guide/datenpool/parents/datenpool-parents-uebersicht.png ':zoom :size=30%')

> **Example 1** - A parent as an independent record.<br><br>
> **Parent**: P12345<br>
> **Variant items**: 12345-white, 12345-red, 12345-black, 12345-blue<br>
> In the data pool, there are 4 variant items stored. Each of the 4 variants has a group ID
  assigned - the number 'P12345'. There is no parent as a separate record.

> **Example 2** - Import file with group IDs<br><br>
> Parents can also be created automatically through the import function in the data pool.
  For this purpose, parents must be present in the import file. Ideally, the description of parents
  should be distinct from the individual variants if possible.
> ![Parent(s) selection](https://wiki.csv4you.com/images/thumb/Parents.png/400px-Parents.png ':zoom :size=30%')

> Please always use the import function when you want to create a larger number of variant items.

#### Group IDs

Group IDs are the most commonly used method for representing variant items. Group IDs are not stored
as independent records; instead, only one group ID is assigned to the variants.

![Overview group IDs](https://data.csv4you.com/media/image/guide/datenpool/parents/datenpool-parents-gruppenids-uebersicht.png ':zoom :size=30%')

Optional, you can also convert group IDs into parents. Use the group function `Create Parent(s) NOW` for this purpose.

![Group IDs selection](https://data.csv4you.com/media/image/guide/datenpool/parents/datenpool-parents-gruppenids-auswahl.png ':zoom :size=30%')
![Group function 'Create parents now'](https://data.csv4you.com/media/image/guide/datenpool/parents/datenpool-parents-gruppenids-auswahl-gruppenfunktion.png ':zoom :size=30%')

> **Example 1** - Group IDs<br><br>
> **Parent**: P12345<br>
> **Variant items**: 12345-white, 12345-red, 12345-black, 12345-blue<br>
> There is one parent and 4 assigned variants. Thus 5 data sets are stored.<br>
  In the 4 variants, the `Parent ID` field contains the value 'P12345'.

> **Example 2** - Import file with parents<br><br>
> Parents can also be automatically created through the import function in the data pool.
  For this purpose, parents must be present in the import file. Ideally, the description of parents
  should differ from the individual variants if possible.<br>
> ![Parent(s) selection](https://wiki.csv4you.com/images/thumb/Group-IDs.png/400px-Group-IDs.png ':zoom :size=30%')

> Please always use the import function when you want to create a larger number of variant items. 

### Assign distinguishing feature to parent

In order to represent a product as a variant, you need to assign the distinguishing feature (size, color, etc.)
to the parent. This can be done directly on the parent or through the group function.

![Parent(s)selection](https://data.csv4you.com/media/image/guide/datenpool/parents/datenpool-parents-auswahl.png ':zoom :size=30%')
![Group function Selection of variant value](https://data.csv4you.com/media/image/guide/datenpool/parents/datenpool-parents-gruppenfunktion.png ':zoom :size=30%')

You can also make these settings for the required properties via import.
Use the following values (must be in the column of the required property of the parent):

- 1 = Use as variant value 1
- 2 = Use as variant value 2
- 3 = Use as variant value 3
- 4 = Use as variant value 4
- 5 = Use as variant value 5
- 99 = Use as variant value

> **Example:** If color is to be used as variant value 1, a 1 must be written in the column.

Currently, this must be done for all parents. If part numbers change or are added in the import file,
you must also adjust the respective parents (if necessary).

***
# Search

Enter a search term or use the search as follows:

- **OR**<br>returns articles where at least one of the search words is found, separated by spaces. Example: 'OR red blue'
- **AND**<br>returns articles where all of the search words are found, separated by spaces. Example: 'AND red blue'

***
# Filter

In addition, there is the possibility to select special search filters.
Thus, targeted search criteria can be selected within the different areas for finding specific records.
To do this, simply click on the button `Filter`.

***
# Group function

The `Group function` button is used for the bundled editing of several products.
First select the desired data sets that you want to edit or delete and then click on the `Group function` button.
Then select a function to be applied to the marked data sets and confirm the action by `Run` it.
