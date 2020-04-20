********
Glossary
********

If a glossary term occurs in the app texts, it is automatically recognized and a link to its definition is added.


1. The Excel File
-----------------

You have to create one Excel file. The Excel file has to be named accoring to the name of your glossary.

+--------------------------------------+---------------------+
| Name of glossary on localcosmos.org  | Name of Excel file  |
+======================================+=====================+
| Glossary                             | ``Glossary.xlsx``   |
+--------------------------------------+---------------------+



2. Excel Content
----------------
Before you continue to read, it is recommended to download the example Excel file. :download:`download example Excel file <_static/Glossary.xlsx>`.

**Important: all content you put into your Excel files has to be in the primary language of your Local Cosmos App**

The Columns
^^^^^^^^^^^

The glossary Excel file has 3 columns: ``Term``, ``Synonyms`` and ``Definition``.


+---+-------------------+-------------------------+---------------------------------------------------------------------------------------------------------------------------+
|   | A                 | B                       | C                                                                                                                         |
+---+-------------------+-------------------------+---------------------------------------------------------------------------------------------------------------------------+
| 1 | Term              | Synonyms                | Definition                                                                                                                |
+===+===================+=========================+===========================================================================================================================+
| 2 | bark              |                         | Bark is the outermost layers of stems and roots of woody plants.                                                          |
+---+-------------------+-------------------------+---------------------------------------------------------------------------------------------------------------------------+
| 3 | Ash dieback       | Hymenoscyphus fraxineus | Hymenoscyphus fraxineus is an Ascomycete fungus that causes ash dieback, a chronic fungal disease of ash trees in Europe. |
+---+-------------------+-------------------------+---------------------------------------------------------------------------------------------------------------------------+
| 4 | Wood-decay fungus | Soft rot \| White rot   | A wood-decay fungus is any species of fungus that digests moist wood, causing it to rot.                                  |
+---+-------------------+-------------------------+---------------------------------------------------------------------------------------------------------------------------+


**Column A: Term**

The term is the text that will be automatically recognized if it occurs in a text of your app. A link to its definition is set, so the user can look it up. This term detection happens during ``build``, and therefore can only be seen after you built your app.


**Column B: Synonyms**

One or more synonyms of the term. Separated by the character "|". Synonyms are also automatically detected in texts, just like terms.


**Column C: Definition**

The definition of the term.


5. Uploading data
-----------------
An uploadable ``Glossary.xlsx`` has to be compressed as a .zip file. The content of this .zip file is only the ``Glossary.xlsx`` file.


