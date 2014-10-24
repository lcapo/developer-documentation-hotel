AvailDestinationTree
====================

**Method Goals**

|

This method returns the tree of destinations accessible from the call
*Avail* .

|

**Request Format**

|

The request does not require any elements empty request.

|

**Response Format**

|

The result returns a list of *DestinationTree* with their
corresponding sub-destinations.

|

*AvailDestinationTreeRQ* Example
--------------------------------

::

    <AvailDestinationTreeRQ>
    </AvailDestinationTreeRQ>

|

*AvailDestinationTreeRQ* Description
------------------------------------

+------------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Element                | Number   | Type     | Description                                                                                 |
+========================+==========+==========+=============================================================================================+
| AvailDestinationTreeRQ | 1        |          | Root node.                                                                                  |
+------------------------+----------+----------+---------------------------------------------------------------------------------------------+

|

*AvailDestinationTreeRS* Example
--------------------------------

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

*AvailDestinationTreeRS* Description
------------------------------------

+------------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Element                | Number   | Type     | Description                                                                                 |
+========================+==========+==========+=============================================================================================+
| AvailDestinationTreeRS | 1        |          | Root node.                                                                                  |
+------------------------+----------+----------+---------------------------------------------------------------------------------------------+

|
