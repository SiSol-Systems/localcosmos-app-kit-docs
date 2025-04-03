Taxon Profiles
==============

1. The Excel Files
------------------

You have to create one Excel file:

1. Excel file containing the Taxon profiles, named exactly like you have named your Taxon Profiles component on localcosmos.org

Naming the Excel file
^^^^^^^^^^^^^^^^^^^^^

The import will only succeed if you name your Excel files correctly. The name of the Excel file containing the Taxon profiles **must match** the name of your Taxon Profiles component on localcosmos.org.

+--------------------------------------------+-----------------------------+
| Name of Taxon Profiles on localcosmos.org  | Name of Excel file          |
+============================================+=============================+
| Species Profiles                           | ``Species Profiles.xlsx``   |
+--------------------------------------------+-----------------------------+

**Important:** Ensure that the file name is spelled exactly as it appears on localcosmos.org, including spaces and capitalization.

2. Taxon Profiles Excel
-----------------------
Before you continue to read, it is recommended to download the example Excel file. :download:`download example Excel file </_static/Taxon Profiles/Taxon profiles.xlsx>`.

**Important: all content you put into your Excel files has to be in the primary language of your Local Cosmos App**

The Taxon Profiles sheet
^^^^^^^^^^^^^^^^^^^^^^^^

The Taxon Profiles Excel requires at exactly one sheet named ``Taxon Profiles``. This is where all your taxon profiles are stored. The sheet has to contain the following columns:

**Example: Sheet "Taxon Profiles" of "Taxon profiles.xlsx":**

.. raw:: html

   <div style="overflow-x: auto; white-space: nowrap;">

+---+---------------------+-------------------+----------------------+-----------------------+---------------------+-----------------------+----------------------------+--------------------------------+-----------------------------------------+---------+-------------------+----------------------------------------+-----------------+
|   | A                   | B                 | C                    | D                     | E                   | F                     | G                          | H                              | I                                       | J       | K                 | L                                      | M               |
+---+---------------------+-------------------+----------------------+-----------------------+---------------------+-----------------------+----------------------------+--------------------------------+-----------------------------------------+---------+-------------------+----------------------------------------+-----------------+
| 1 | Scientific Name     | Author (optional) | Taxonomic Source     | Morphotype (optional) | short_profile       | text                  | text                       | text                           | text                                    | image   | seo               | seo                                    | tags            |
+---+---------------------+-------------------+----------------------+-----------------------+---------------------+-----------------------+----------------------------+--------------------------------+-----------------------------------------+---------+-------------------+----------------------------------------+-----------------+
| 2 |                     |                   |                      |                       |                     | Interesting facts     | Forest protection          | Occurrence                     | Tree as habitat                         |         | title             | meta_description                       |                 |
+---+---------------------+-------------------+----------------------+-----------------------+---------------------+-----------------------+----------------------------+--------------------------------+-----------------------------------------+---------+-------------------+----------------------------------------+-----------------+
| 3 |                     |                   |                      |                       |                     |                       |                            |                                | Ecosystem roles                         |         |                   |                                        |                 |
+===+=====================+===================+======================+=======================+=====================+=======================+============================+================================+=========================================+=========+===================+========================================+=================+
| 4 | Quercus robur       |                   | taxonomy.sources.col |                       | strong, long-lived. | Acorns feed wildlife. | Stores carbon, stabilizes. | Widespread, Europe, woodlands. | Quercus robur: Shelters birds, insects. | Oak.jpg | English Oak Guide | English oak: a strong, long-lived tree | tree, deciduous |
+---+---------------------+-------------------+----------------------+-----------------------+---------------------+-----------------------+----------------------------+--------------------------------+-----------------------------------------+---------+-------------------+----------------------------------------+-----------------+
| 5 | Fraxinus excelsior  |                   | taxonomy.sources.col |                       | tall, resilient.    | Wood used for tools.  |                            | Common, Europe, forests.       |                                         |         |                   |                                        |                 |
+---+---------------------+-------------------+----------------------+-----------------------+---------------------+-----------------------+----------------------------+--------------------------------+-----------------------------------------+---------+-------------------+----------------------------------------+-----------------+

.. raw:: html

   </div>

Rows of the Taxon Profiles sheet
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The first three rows are for definitions. From the fourth row on, the taxon profiles are listed.

**Row 1: Data types**

The first row contains the data types of the columns. Mandatory columns are:

* **Scientific Name**: the scientific name of the taxon.
* **Author (optional)**: the author of the scientific name.
* **Taxonomic Source**: the source of the taxonomic classification.
* **Morphotype (optional)**: the morphotype of the taxon.

These columns have to be present in your spreadsheet. This does not mean that you have to provide content for these columns in the taxon profile rows (rows 4 on). You can leave them empty. But you have to provide the column names in row 1.
This means, that the first four cells of row one are fixed cells. You cannot change the content of these cells. The other cells are optional and can be changed or deleted.
You can fill the columns from E onwards with the data types you want.

Optional columns are:
* **short_profile**: a short profile of the taxon. You can only have one short_profile column.
* **text**: a text about the taxon. You can have as many text columns as you want.
* **image**: an image of the taxon. You can have as many image columns as you want.
* **seo**: a column for SEO. Requires further definition in row 2.
* **tags**: a column for tags. You can only have one tag column.

**Row 2: Further definition of the Data types defined in row 1**

Some Data types require further definition in row 2. The following data types require further definition:
* **text**: the text column requires a title. The title is the text that will be displayed in the app. The title is mandatory.
* **seo**: the SEO column requires further definition in row 2. You have two options: "title" and "meta_description".

**Row 3: Further definition of the Data types defined in row 1**

THe Data type text can have further definition in row 3. You can group texts in categories. This category is listed in row 3. You can have as many categories as you want. The categories are optional.

**Row 4 on: The taxon profiles**

The taxon profiles are listed from row 4 on. One row stands for the profile of one taxon. The first four columns have a fixed type. ``Scientific Name`` and ``Taxonomic Source`` are mandatory. All other columns are optional.


The Images sheet
^^^^^^^^^^^^^^^^

The images have to reside in a sheet called ``Taxon Profile Images``. Read the images sheet specification here: :doc:`images_sheet`.



3. images folder
----------------
You upload your Taxon Profiles as a ``.zip`` file. Within this ``.zip`` file, you can supply images for your Taxon Profiles.
The images have to be in a folder called ``images``.

Example: ``images/Oak.jpg```

For the example Excel file, you would have a folder structure similar to this:

| nature_guide
| ├── Identify Trees.xlsx
| ├── images          
| │     ├── Oak.jpg

Each image has to be of square dimensions. The recommended size is 1000x1000 pixels. The image format can be .jpg, .webp or .png.
The maximum allowed size is 2000x2000 pixels. If you upload too many images, the upload will fail.