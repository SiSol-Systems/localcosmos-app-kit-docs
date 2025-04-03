Importing images
================

Local Cosmos Excel import feature the possibility to import images from your local computer.
The images are stored in the ``images`` folder of your .zip file. The images are linked to the data in the Excel file.
Depending on the type of data you are importing, the images are linked in different spreadsheets:

* **Taxon Profiles**: the images are linked in the ``Taxon Profile Images`` sheet. An example can be downloaded here: :download:`download example Excel file </_static/Taxon Profiles/Taxon profiles.xlsx>`.


Images sheet specification
--------------------------

Each images sheet has to have the following columns:

* **Identifier**: the identifier of the image. This is the name of the image file with its extension. The identifier has to be unique in the images sheet.
* **Author**: the author of the image. This is required for all images.
* **Licence**: the licence of the image. This is required for all images.
* **Licence version**: the version of the licence. This is required for all images.
* **Link to source image (optional)**: the link to the source image. This is optional.
* **Title (optional)**: the title of the image. This is optional.
* **Caption (optional)**: the caption of the image. This is optional.
* **Alt text (optional)**: the alt text of the image. This is optional.
* **Primary image (optional)**: If you have more than one image for an entity (e.g. a Taxon profile), you can mark one of them as the primary image. This is optional.


**Example: Sheet "Taxon Profile Images" of "Taxon profiles.xslx":**

.. raw:: html

   <div style="overflow-x: auto; white-space: nowrap;">

+---+-------------+---------------+----------+-----------------+---------------------------------+------------------------+------------------------------------------------+---------------------------------------------------------------------+--------------------------+
|   | A           | B             | C        | D               | E                               | F                      | G                                              | H                                                                   |                          |
+---+-------------+---------------+----------+-----------------+---------------------------------+------------------------+------------------------------------------------+---------------------------------------------------------------------+--------------------------+
| 1 | Identifier  | Author        | Licence  | Licence version | Link to source image (optional) | Title (optional)       | Caption (optoinal)                             | Alt text (optional)                                                 | Primary image (optional) |
+===+=============+===============+==========+=================+=================================+========================+================================================+=====================================================================+==========================+
| 2 | Oak.jpg     | Pablo Picasso | CC BY-SA | 4.0             |                                 | Quercus Robur Oak Tree | Majestic oak tree supporting diverse wildlife. | Oak tree in lush woodland, providing habitat for birds and insects. |                          |
+---+-------------+---------------+----------+-----------------+---------------------------------+------------------------+------------------------------------------------+---------------------------------------------------------------------+--------------------------+

.. raw:: html

   </div>

How images are imported
-----------------------
Images are imported from the ``images`` folder of your .zip file. You do not have to upload your images every time.
If an image is listed in the ``images`` spreadsheet but no file is found in the images folder, the image will not be imported.
If you uploaded this file earlier, the existing image will not be deleted. This means that you can update your images with the first upload and then leave image files out of the zip files for the second upload.
You always have to supply an ``images`` folder, even if it is empty. The images folder has to be in the root of your .zip file.