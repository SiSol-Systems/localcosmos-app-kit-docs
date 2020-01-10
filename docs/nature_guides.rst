*************
Nature Guides
*************

Nature Guides are identification keys or species lists.

1. Import from Excel
====================
To import an identification key from Excel, you need the following skills:

* creating folders
* basic Excel, working with multiple spreadsheets, cell contents and cell backgrounds
* basic understanding of tree structures
* creating .xls or .xlsx files
* creating .zip files
* creating .jpg or .png images with specific dimensions

1.1 The Excel Files
-------------------

You have to create two Excel files:

1. excel file containing the Nature Guide
2. excel file containing image licences

Naming the Excel files
^^^^^^^^^^^^^^^^^^^^^^

The import will only succeed if you named your Excel files correctly. The name of the Excel file containing the Nature Guide has to match the name of the Nature Guide you created on localcosmos.org.

+------------------------------------------+-------------------------------+
| Name of Nature Guide on localcosmos.org  | Name of Excel file            |
+==========================================+===============================+
| Identify trees                           | ``Identify trees.xls`` or     |
|                                          | ``Identify trees.xlsx``       |
+------------------------------------------+----------------------------- -+

The Excel file containing the image licences has to be named ``Image_Licences.xlsx`` or ``Image_Licences.xls``.


1.2 Nature Guide Excel
----------------------
Before you continue to read, it is recommended to download the example Excel file. :download:`download example Excel file <_static/Identify trees.xlsx>`.

**Important: all content you put into your Excel files has to be in the primary language of your Local Cosmos App**

The Tree sheet
^^^^^^^^^^^^^^

The Nature Guide Excel requires at exactly one sheet named ``Tree``. This sheet defines the identification tree. A tree with only one level would result in a simple species list. Each line of this sheet equals one entry in the identification tree - except the first one which defines the columns.

**Columns of the Tree sheet**

**Column A: Node Name**

A Node is a leveled entry in the identification tree and can have any name. It can be something like ``Conifers``, ``Whales`` or even ``Stones``. It does not have to be a biological taxon. 


**Column B: Parent Node**

The parent node of this node. If empty, this node will be displayed on the first identification step. If a Parent Node is specified, this node will appear after the user selected the specified Parent Node.


**Column C: Taxonomic Source**

The columns ``Taxonomic Source`` and ``Scientific Name`` only should be filled if the node is an identification result.

Currently, only two taxonomic sources are available, **Catalogue Of Life** and **Custom taxonomy**. Therefore, this cell has to be filled with ``taxonomy.sources.col`` (recommended) or ``taxonomy.sources.custom``, if you supply a custom taxonomy. Leave empty if your node is not a biological taxon or if you do not want to use taxonomic features.


**Column D: Scientific Name**

The columns ``Taxonomic Source`` and ``Scientific Name`` only should be filled if the node is an identification result. Fill in a scientific name **without author** into this cell. Example: ``Lacerta agilis``.


**Column E: Decision Rule**

A ``Decision Rule`` is a rule when to decide to choose this taxon or information how to identify it. Decision Rules are optional and make sense if you do not want to use a trait based itentification for this level of the identification tree.


Matrix Sheets
^^^^^^^^^^^^^
A matrix sheet is used to define an identification matrix for a specific level of the identifcation tree. The level the matrix is used for is specified by a parent node. The name of the matrix sheet inside your Excel document has to be set accordingly.

+--------------------------+----------------------------+
| Name of Parent Node      | Name of Matrix Sheet       |
+==========================+============================+
| Deciduous Trees          | ``Matrix_Deciduous Trees`` |
+--------------------------+----------------------------+

In the example Excel file, a matrix sheet for all deciduous trees is used, and thus is named after the Parent Node ``Deciduous Trees``.

Nodes are entered in Column A, Matrix Filters are entered from Column B onwards.

Within the matrix sheet, the first 4 rows are used to define the matrix filters (=traits).

* row 1: Name of the matrix filter (trait)
* row 2: Type of the matrix filter. Available matrix filter types are: ``DescriptiveTextAndImages``, ``Color``, ``Range``, ``Number``, ``Taxon``
* row 3 (optional): unit, for example ``cm``
* row 4: step of the Range. Only applies if row 2 (type) is ``Range``. Defines the step of the rendered slider. 

Row 5 onwards are used to assign values to nodes. If you want to assign more than one value to a node, use the OR seprator ``|``. For example ``oval | wavy``.

You can create one Matrix Sheet for each Parent Node, but no Matrix Sheet is required.


Matrix Filter Types
^^^^^^^^^^^^^^^^^^^
**DescriptiveTextAndImages**

A text with an image. Suitable for traits like "Shape of the leaf".


**Color**

Colors consist of a name and a color code. Both are defined in the ``Colors Sheet``. In the Matrix Sheet you only reference colors by name, as defined in the ``Colors Sheet``.


**Range**

A range of numbers, for example from 10cm to 50cm. Also takes step, defined in row 4. If the step is ``1``, the range slider, which the app user uses to select a value, would consist of the numbers 10, 11, 12, ... 48, 49, 50.


**Number**

Numbers that are no ranges, for example the numbers 2,4,5,8.


**Taxon**

Taxonomic filters are defined in the ``Taxonomic Filters Sheet``. You can only add a taxonomic filter, but you cannot assign values in the Matrix Sheet as you can with the other matrix filters. Taxonomic Filters work automatically using the taxonomic backend of your App.


Colors Sheet
^^^^^^^^^^^^
The Colors Sheet is used to define colors. Column A sets the name of the color. Column B sets the actual color by using a cell background.


Taxonomic Filters Sheet
^^^^^^^^^^^^^^^^^^^^^^^
This sheet has to be named ``Taxonomic Filters``, and your Excel file may only have one ``Taxonomic Filters`` sheet.


1.3 Images
----------
You upload your Nature Guide as a ``.zip`` file. Within this ``.zip`` file, you can supply images for the following assets:

* Nodes
* Matrix Filters of the type ``DesctiptiveTextAndImages``

All images have to reside in a folder called ``images``. All images for Nodes have to reside in ``images/Tree``. All images for matrix filters have to reside in the folder ``images/Matrix_<parent_node>/<matrix_filter_name>/``, and the name of the image has to match the value. Example: ``images/Matrix_Deciduous Trees/Shape of the leaf/heart shaped.jpg```

In the example Excel file, you would have a folder structure similar to this:

| nature_guide
| ├── Identify Trees.xlsx
| ├── images          
| │     ├── Tree
| │     │     ├── Conifers.jpg
| │     │     ├── Deciduous Trees.jpg
| │     │     ├── Oak.jpg
| │     │
| │     ├── Matrix_Deciduous Trees
| │     │     ├── Shape of the leaf
| │     │     │   ├── heart shaped.jpg



1.4 Image Licences Excel
------------------------
You have to supply an image licence alongside its creator for all your images. The image licences are provided by the file ``Image Licences.xlsx``. :download:`download example Excel file <_static/Image Licences.xlsx>`.

You have to supply at least the columns ``Image`` (column A), ``Licence`` (column B) and ``Creator`` (column C). ``Creator link`` (column D) is optional.

The ``Image`` column expects paths to the image, relative to your ``image`` folder, where the images reside.

Examples: ``Tree/Conifers.jpg`` or ``Matrix_Deciduous Trees/Shape of the leaf/heart_shaped.jpg``.


Only short licence names are allowed for the ``Licence`` Column. Available Licences are:

+-------------------------------------------------------+----------------------------+
| Full Licence Name                                     | Short name                 |
+=======================================================+============================+
| Public Domain Dedication                              | CC0                        |
+-------------------------------------------------------+----------------------------+
| Creative Commons Attribution                          | CC BY                      |
+-------------------------------------------------------+----------------------------+
| Creative Commons Attribution-ShareAlike               | CC BY-SA                   |
+-------------------------------------------------------+----------------------------+
| Creative Commons Attribution-NoDerivs                 | CC BY-ND                   |
+-------------------------------------------------------+----------------------------+
| Creative Commons Attribution-NonCommercial            | CC BY-NC                   |
+-------------------------------------------------------+----------------------------+
| Creative Commons Attribution-NonCommercial-ShareAlike | CC BY-NC-SA                |
+-------------------------------------------------------+----------------------------+
| Creative Commons Attribution-NonCommercial-NoDerivs   | CC BY-NC-ND                |
+-------------------------------------------------------+----------------------------+
| Public Domain Mark                                    | PDM                        |
+-------------------------------------------------------+----------------------------+


1.5 Uploading data
------------------
All uploadable Nature Guides consist of the folder ``images``, the file ``<name_of_nature_guide>.xlsx``, and the file ``Image Licences.xlsx``. You have to create a ``.zip`` file containing these 3 items.

:download:`download example zip file <_static/Identify Trees.zip>`.
