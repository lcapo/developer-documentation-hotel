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

**Remarks**

The maximum time, that is permited in our system, before the connection is closed,  is of **240000** miliseconds.

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

Detailled description
---------------------

::

    <AvailDestinationTreeRS>
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

In availDestinationTree you will always receive zones and cities with an attackable availability ( the
difference between availDestinationTree and GeographicDestinationTree is that in GeographicDestinationTree
there is a parameter indicating the avail with true or false )


*Distinction Zone & City:*

If DestinationTree code has DestinationLeafs ( children ) like in this case 
"<DestinationTree code = "BAL" name = "Baleares">" has two children called <DestinationLeaf code = "PAL0"/> and
<DestinationLeaf code = "ALC0"/> then this will indicate that it is a zone node.  In this case, if you want to 
do an avail with this code you will need to indicate it as a zone type(ZON).

If DestinationTree code has no DestinationLeafs ( no children ) like in this case <DestinationLeaf code = "PAL0"/> 
and <DestinationLeaf code = "ALC0"/> then this will indicate that is is a city code. In this case, if you want to do an avail 
with these codes you will need to indicate them as city types (CTY)

In conclusion, if the DestinationTree code has children, then it is a **ZONE**. If the DestinationTree code 
has no children then this will indicate a **CITY**.

|
