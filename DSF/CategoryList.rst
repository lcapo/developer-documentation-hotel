.. highlight:: xml

CategoryList
============

|

Method Goals
------------

This method aims to return a list of the available categories, which
will be used in the list of hotels response.

|

Request Format
--------------

The request does not require any elements empty request.

|

Response Format
---------------

The result returns a list of *Category* .

|

Remarks
-------

The maximum time, that is permitted in our system, before the connection is closed,  is of **240000** milliseconds.

|


CategoryListRQ Example
----------------------

::

    <CategoryListRQ>
    </CategoryListRQ>

|

CategoryListRQ Description
--------------------------

+---------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Element             | Number   | Type     | Description                                                                                 |
+=====================+==========+==========+=============================================================================================+
| CategoryListRQ      | 1        |          | Root node.                                                                                  |
+---------------------+----------+----------+---------------------------------------------------------------------------------------------+

|

CategoryListRS Example
----------------------

::

    <CategoryListRS>
        <Categories>
            <Category>
                <Code>3*</Code>
                <Name>3 Estrellas</Name>
            </Category>
            <Category>
                <Code>3L</Code>
                <Name>3 Llaves</Name>
            </Category>
            ...
            <Category/>
        </Categories>
    </CategoryListRS>

|

CategoryListRS Description
--------------------------

+---------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Element             | Number   | Type     | Description                                                                                 |
+=====================+==========+==========+=============================================================================================+
| CategoryListRQ      | 1        |          | Root node.                                                                                  |
+---------------------+----------+----------+---------------------------------------------------------------------------------------------+

|
