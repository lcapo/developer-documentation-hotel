GeographicDestinationTree
=========================

**Method Goals**

|

This method returns the provider's geographic tree where each node
indicates whether the call is accessible from availability.

|

**Request Format**

|

The request not requires any element, it is empty.

|

**Response Format**

|

The result returns a list of *DestinationTree* with corresponding
sub-destinations.

|

*GeographicDestinationTreeRQ* Example
-------------------------------------

::

    <GeographicDestinationTreeRQ>
    </GeographicDestinationTreeRQ>

|

*GeographicDestinationTreeRQ* Description
-----------------------------------------

+----------------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Element                    | Number   | Type     | Description                                                                                 |
+============================+==========+==========+=============================================================================================+
| GeographicDestinationTreeRQ| 1        |          | Root node.                                                                                  |
+----------------------------+----------+----------+---------------------------------------------------------------------------------------------+

|

*GeographicDestinationTreeRS* Example
-------------------------------------

::

    <GeographicDestinationTreeRS>
        <DestinationTree code = "ES" name = "España" avail = "False">
            <DestinationLeaf code = "BAL"/>
            <DestinationLeaf code = "AST"/>
            <DestinationLeaf code = "AND"/>
        </DestinationTree>
        <DestinationTree code= "IT" name = "Italia" avail = "False">
            <DestinationLeaf code = "AA"/>
            <DestinationLeaf code = "BB"/>
            . . .
        </DestinationTree>
        <DestinationTree code = "EN" name = "England" avail = "False">. . .</DestinationTree>
        <DestinationTree code = "BAL" name = "Baleares" avail = "True">
            <DestinationLeaf code = "PAL0"/>
            <DestinationLeaf code = "ALC0"/>
        </DestinationTree>
        <DestinationTree code = "AST" name = "Asturias" avail = "True"/>
        <DestinationTree code = "AND" name = "Andalucia" avail = "True"/>
        . . .
        <DestinationTree code = "PAL0" name = "Palma de Mallorca" avail = " True"/>
        <DestinationTree code = "ALC0" name = "Alcudia" avail = " True"/>
        . . .
    </GeographicDestinationTreeRS>

|

*GeographicDestinationTreeRS* Description
-----------------------------------------

+----------------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Element                    | Number   | Type     | Description                                                                                 |
+============================+==========+==========+=============================================================================================+
| GeographicDestinationTreeRS| 1        |          | Root node.                                                                                  |
+----------------------------+----------+----------+---------------------------------------------------------------------------------------------+

|

Detailled description
---------------------

**Location type:**

**Standard case:**

::

    <DestinationTree code = "ES" name = "Spain" avail = "false">
        <DestinationLeaf code = "BAL"/>
    </DestinationTree>
    <DestinationTree code = "BAL" name = "Balearic" avail = "true">
        <DestinationLeaf code = "PMI"/>
        <DestinationLeaf code = "ALC"/>
        <DestinationLeaf code = "CON"/>
    </DestinationTree>
    <DestinationTree code = "PMI" name = "Palma" avail = "true"/>
    <DestinationTree code = "ALC" name = "Alcudia" avail = "true"/>
    <DestinationTree code = "CON" name = "Consell" avail = "true"/>

|

This example starts with "<DestinationTree code = "ES" name = "Spain" avail = "false">" where it is indicating that Spain hasn't
got availability because it is false. It also has one child node called <DestinationLeaf code = "BAL"/>. 

This child "BAL" has avail = true, meaning it is possible to do an availability. This node "BAL" also has three other 
children called PMI, ALC, CON. Ergo, If DestinationTree code as avail = "true" and also, at the same time, has one or more
children then this will indicate that this node is a Zone. In this case, if you want to do an avail with this code you will
need to indicate it as a zone type(ZON). 

These three children PMI, ALC, CON also are available because they are true, but the have no DestinationLeaf (or children). 
This indicates that these nodes are cities. In this case, if you want to do an avail with these codes you will need to indicate
them as city types (CTY)  

In conclusion, if the DestinationTree code has avail true and children, means it is a **ZONE**. If the DestinationTree code has
avail true, but no children this will indicate a **CITY**.   

|

**Specific case:**

::

    <DestinationTree code = "ES" name = "Spain" avail = "false">
        <DestinationLeaf code = "BAL"/>
    </DestinationTree>
    <DestinationTree code = "BAL" name = "Balearic" avail = "true">
        <DestinationLeaf code = "PMI"/>
        <DestinationLeaf code = "ALC"/>
        <DestinationLeaf code = "CON"/>
    </DestinationTree>
    <DestinationTree code = "ALC" name = "Alcudia" avail = "true"/>
    <DestinationTree code = "CON" name = "Consell" avail = "true"/>
    <DestinationTree code = "PMI" name = "Palma" avail = "true"/>
        <DestinationLeaf code = "SAR"/>
        <DestinationLeaf code = "IND"/>
    <DestinationTree code = "SAR" name = "Son Sardina" avail = "false"/>
    <DestinationTree code = "IND" name = "Indioteria" avail = "false"/>
    
There is also another possible case where the city isn't the lowest child or DestinationLeaf code and has children of their own. 
Meaning the cities will have DestinationLeaf code (children) that will represent neighborhoods. Like in this example 
"Son Sardina" and "Indioteria" represent neighborhoods of the city Palma of Mallorca. Even though "Son Sardina" and "Indioteria"
are the lowest DestinationLeaf ( child ) these codes can't represent as cities codes, because they haven't got attackable 
Avail, because their Avail is false.

So even if PMI has DestinationLeafs he will be the city code because his DestinationLeafs have false avail.
