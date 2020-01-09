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
You can download an example :download:`here <_static/Identify trees.xlsx>`.

**Important: all content you put into your Excel files has to be in the primary language of your Local Cosmos App**

The Tree sheet
^^^^^^^^^^^^^^

The Nature Guide Excel requires at exactly one sheet named ``Tree``. This sheet defines the identification tree. A tree with only one level would result in a simple species list. Each line of this sheet equals one entry in the identification tree - except the first one which defines the columns.

**Columns of the Tree sheet**

**Column A: Node Name**

A Node is a leveled entry in the identification tree and can have any name. It can be something like ``Conifers``, ``Whales`` or even ``Stones``. It does not have to be a biological taxon. 


**Column B: Parent Node**

The parent of the node. If empty, this node will be displayed on the first identification step. If a Parent Node is specified, this node will appear after the user selected the specified Parent Node.


**Column C: Taxonomic Source**

The columns ``Taxonomic Source`` and ``Scientific Name`` only should be filled if the node is an identification result.

Currently, only two taxonomic sources are available, **Catalogue Of Life** and **Custom taxonomy**. Therefore, this cell has to be filled with ``taxonomy.sources.col`` (recommended) or ``taxonomy.sources.custom``, if you supply a custom taxonomy. Leave empty if your node is not a biological taxon or if you do not want to use taxonomic features.


**Column D: Scientific Name**

The columns ``Taxonomic Source`` and ``Scientific Name`` only should be filled if the node is an identification result. Fill in a scientific name **without author** into this cell. Example: ``Lacerta agilis``.


**Column E: Decision Rule**

A ``Decision Rule`` is a rule when to decide to choose this taxon or information how to identify it. Decision Rules are optional and make sense if you do not want to use a trait based itentification for this level of the identification tree.


Matrix Sheets
^^^^^^^^^^^^^


Colors Sheet
^^^^^^^^^^^^


Taxonomic Filters Sheet
^^^^^^^^^^^^^^^^^^^^^^^


1.3 Image Licences Excel
------------------------
