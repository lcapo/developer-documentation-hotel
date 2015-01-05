.. highlight:: xml

AvailDestinationTree
====================

|

Method Goals
------------

This method returns the tree of destinations accessible from the call
*Avail* .

|

Request Format
--------------

The request does not require any elements empty request.

|

Response Format
---------------

The result returns a list of *DestinationTree* with their
corresponding sub-destinations.

|

Remarks
-------

The maximum time, that is permitted in our system, before the connection is closed,  is of **240000** milliseconds.

|

AvailDestinationTreeRQ Example
------------------------------

::

    <AvailDestinationTreeRQ>
    </AvailDestinationTreeRQ>

|

AvailDestinationTreeRQ Description
----------------------------------

+------------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Element                | Number   | Type     | Description                                                                                 |
+========================+==========+==========+=============================================================================================+
| AvailDestinationTreeRQ | 1        |          | Root node.                                                                                  |
+------------------------+----------+----------+---------------------------------------------------------------------------------------------+

|

AvailDestinationTreeRS Example
------------------------------

::

    <AvailDestinationTreeRS>
        <DestinationTree code = "ES" name = "España">
            <DestinationLeaf code = "BAL"/>
            <DestinationLeaf code = "AST"/>
            <DestinationLeaf code = "AND"/>
        </DestinationTree>
        <DestinationTree code = "IT" name = "Italia">
            <DestinationLeaf code = "AA"/>
            <DestinationLeaf code = "BB"/>
            . . .
        </DestinationTree>
        <DestinationTree code = "EN" name = "England">. . .    </DestinationTree>
        <DestinationTree code = "BAL" name = "Baleares">
            <DestinationLeaf code = "PAL0"/>
            <DestinationLeaf code = "ALC0"/>
        </DestinationTree>
        <DestinationTree code = "AST" name = "Asturias"/>
        <DestinationTree code = "AND" name = "Andalucia"/>
        <DestinationTree code = "PAL0" name = "Palma de Mallorca"/>
        <DestinationTree codigo = "ALC0" name = "Alcudia"/>
        . . .
    </AvailDestinationTreeRS>

|

AvailDestinationTreeRS Description
----------------------------------

+------------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Element                | Number   | Type     | Description                                                                                 |
+========================+==========+==========+=============================================================================================+
| AvailDestinationTreeRS | 1        |          | Root node.                                                                                  |
+------------------------+----------+----------+---------------------------------------------------------------------------------------------+
| DestinationTree        | 1..n     |          | Father node.                                                                                |
+------------------------+----------+----------+---------------------------------------------------------------------------------------------+
| DestinationLeaf        | 0..1     |          | Child node.                                                                                 |
+------------------------+----------+----------+---------------------------------------------------------------------------------------------+

|

Detailed description
--------------------

::

    <AvailDestinationTreeRS>
        <DestinationTree code = "BAL" name = "Baleares">
            <DestinationLeaf code = "PAL0"/>
            <DestinationLeaf code = "ALC0"/>
        </DestinationTree>
        <DestinationTree code = "AST" name = "Asturias"/>
        <DestinationTree code = "AND" name = "Andalucia"/>
        <DestinationTree code = "PAL0" name = "Palma de Mallorca"/>
        <DestinationTree code = "ALC0" name = "Alcudia"/>
        . . .
    </AvailDestinationTreeRS>
    
|

There is one primordial definition that needs to be clear to understand the difference in city and zone: types of nodes.

There are two types of nodes. First there is the parent node, also named DestinationTree node, and the child node, also named Destination leaf node. A parent
can have zero to n children ( 0..n ) and a child will have only one parent ( 1..1 ). For example, the DestinationTree code = "ES" is the parent of the DestinationLeaf
code = "BAL", "AST" and "AND" and at the same time DestinationTree code = "BAL" is also a the parent of the DestinationLeaf code = "PAL0" and "ALC0", and so on. 


Therefore:

	* **City:** Lowest node. 

	* **Zone:** Not the lowest node.

|

.. image:: ../images/diagrama2.png
    :align: center 

|
	
.. note:: All of the zones that appear in this particular call ( DestinationsTree call ) are all attackable nodes on an availability level.  

|
