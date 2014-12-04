.. highlight:: xml

GeographicDestinationTree
=========================

|

Method Goals
------------

This method returns the provider's geographic tree where each node
indicates whether the call is accessible from availability
which is indicate with a parameter with values of true and false. 
The main difference between the methods GeographicalTree and
DestinationTree is that GeographicalTree has this boolean 
parameter.


|

Request Format
--------------

The request not requires any element, it is empty.

|

Response Format
---------------

The result returns a list of *DestinationTree* with corresponding
sub-destinations.

|

Remarks
-------

The maximum time, that is permitted in our system, before the connection is closed,  is of **240000** milliseconds.

|

GeographicDestinationTreeRQ Example
-----------------------------------

::

    <GeographicDestinationTreeRQ>
    </GeographicDestinationTreeRQ>

|

GeographicDestinationTreeRQ Description
---------------------------------------

+----------------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Element                    | Number   | Type     | Description                                                                                 |
+============================+==========+==========+=============================================================================================+
| GeographicDestinationTreeRQ| 1        |          | Root node.                                                                                  |
+----------------------------+----------+----------+---------------------------------------------------------------------------------------------+

|

GeographicDestinationTreeRS Example
-----------------------------------

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

GeographicDestinationTreeRS Description
---------------------------------------

+----------------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Element                    | Number   | Type     | Description                                                                                 |
+============================+==========+==========+=============================================================================================+
| GeographicDestinationTreeRS| 1        |          | Root node.                                                                                  |
+----------------------------+----------+----------+---------------------------------------------------------------------------------------------+
| DestinationTree            | 1..n     |          | Father node.                                                                                |
+----------------------------+----------+----------+---------------------------------------------------------------------------------------------+
| DestinationLeaf            | 0..1     |          | Child node.                                                                                 |
+----------------------------+----------+----------+---------------------------------------------------------------------------------------------+

|

Detailed description
--------------------

**Location type:**

**Standard case:**

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

This example starts with "<DestinationTree code = "ES" name = "Spain" avail = "false">" where it is indicating that Spain hasn't
got availability because it is false. It also has three children node called <DestinationLeaf code = "BAL"/>, 
<DestinationLeaf code = "AST"/> and <DestinationLeaf code = "AND"/>. 

The child "BAL" has avail = true, meaning it is possible to do an availability. This node "BAL" also has two other 
children called PAL0 and ALC0. Ergo, If DestinationTree code as avail = "true" and also, at the same time, has one or more
children then this will indicate that this is a Zone node. In this case, if you want to do an avail with this code you will
need to indicate it as a zone type(ZON). 

These two children PAL0 and ALC0, also have available because they are true, but they have no DestinationLeaf (or children). 
This indicates that these nodes are cities. In this case, if you want to do an avail with these codes you will need to indicate
them as city types (CTY)  

In conclusion, if the DestinationTree code has avail true and children, then it is a **ZONE**. If the DestinationTree code has
avail true, but no children then this will indicate a **CITY**.   

|

**Specific case:**

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
		<DestinationTree code = "PAL0" name = "Palma de Mallorca" avail = " True"/>
			<DestinationLeaf code = "SAR"/>
			<DestinationLeaf code = "IND"/>
    
        <DestinationTree code = "AST" name = "Asturias" avail = "True"/>
        <DestinationTree code = "AND" name = "Andalucia" avail = "True"/>
        . . .
        <DestinationTree code = "ALC0" name = "Alcudia" avail = " True"/>
		<DestinationTree code = "SAR" name = "Son Sardina" avail = "false"/>
		<DestinationTree code = "IND" name = "Indioteria" avail = "false"/>
        . . .
    </GeographicDestinationTreeRS>
    
|
    
There is also another possible case where the city isn't the lowest child or DestinationLeaf code and has children of their own. 
Meaning the cities will have DestinationLeaf code (children) that will represent neighbourhoods. Like in this example 
"Son Sardina" and "Indioteria" represent neighbourhoods of the city Palma of Mallorca. Even though "Son Sardina" and "Indioteria"
are the lowest DestinationLeaf ( child ) these codes can't represent as cities codes, because they haven't got attackable 
Avail, because their Avail is false.

So even if PAL0 has DestinationLeafs he will be the city code because his DestinationLeafs have false avail.

|
