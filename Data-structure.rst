.. highlight:: xml

##############
Data Structure
##############

The structure of the API specification follows a standard. This document intends to explain every aspect of this structure and their fields.
The integration will have the following methods:

|

+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| Method                                                       | Input                         | Output                        | Required   | Description                                  |
+==============================================================+===============================+===============================+============+==============================================+
| `AvailDestinationTree <#availdestinationtree>`__             | AvailDestinationTreeRQ        | AvailDestinationTreeRS        | No         | Returns a tree of available destinations     |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `GeographicDestinationTree <#geographicdestinationtree>`__   | GeographicDestinationTreeRQ   | GeographicDestinationTreeRS   | Yes        | Returns a tree of provider destinations      |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `HotelList <#hotellist>`__                                   | HotelListRQ                   | HotelListRS                   | Yes        | Returns a list of available hotels           |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `DescriptiveInfo <#descriptiveinfo>`__                       | DescriptiveInfoRQ             | DescriptiveInfoRS             | Yes        | Returns DSF information per DSF          |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `RoomList <#roomlist>`__                                     | RoomListRQ                    | RoomListRS                    | No         | Returns available room types                 |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `MealPlanList <#mealplanlist>`__                             | MealPlanListRQ                | MealPlanListRS                | Yes        | Returns a list of available boards           |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `CategoryList <#categorylist>`__                             | CategoryListRQ                | CategoryListRS                | Yes        | Returns a list of available categories       |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `Avail <#avail>`__                                           | AvailRQ                       | AvailRS                       | Yes        | Makes an availability call                   |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `Valuation <#valuation>`__                                   | ValuationRQ                   | ValuationRS                   | Yes        | Gets a booking quote (pre-book)              |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `Reservation <#reservation>`__                               | ReservationRQ                 | ReservationRS                 | Yes        | Makes a booking                              |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `Cancel <#cancel>`__                                         | CancelRQ                      | CancelRS                      | No         | Cancels a booking                            |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `ReservationRead <#reservationread>`__                       | ReservationReadRQ             | ReservationReadRS             | No         | Gets booking details                         |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `ReservationList <#reservationlist>`__                       | ReservationListRQ             | ReservationListRS             | No         | Gets a list of bookings                      |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `RuntimeConfiguration <#runtimeconfiguration>`__             | RuntimeConfigurationRQ        | RuntimeConfigurationRS        | Yes        | Gets the provider's run-time configuration   |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `StaticConfiguration <#staticconfiguration>`__               | StaticConfigurationRQ         | StaticConfigurationRS         | Yes        | Gets the provider's static configuration     |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `ModifyValuation <#modifyvaluation>`__                       | ModifyValuationRQ             | ModifyValuationRS             | No         | Valuation a possible booking modification    |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+
| `ModifyReservation <#modifyreservation>`__                   | ModifyReservationRQ           | ModifyReservationRS           | No         | Confirm a booking modification               |
+--------------------------------------------------------------+-------------------------------+-------------------------------+------------+----------------------------------------------+

Each request sent to the **service url** requires a node called
*rqXML*. Inside this node travels the current method's Input object.

|


The data structure will always have common elements in all objects and
the specific objects related to the operation

|

.. toctree::
  :maxdepth: 3
  :numbered:
  
  Common-Elements<./DSF/Common-Elements.rst>
  Avail<./DSF/Avail.rst>
  Valuation<./DSF/Valuation.rst>
  Reservation<./DSF/Reservation.rst>
  ReservationRead<./DSF/ReservationRead.rst>
  ReservationList<./DSF/ReservationList.rst>
  Cancel<./DSF/Cancel.rst>
  HotelList<./DSF/HotelList.rst>
  DescriptiveInfo<./DSF/DescriptiveInfo.rst>
  DestinationTree<./DSF/AvailDestinationTree.rst>
  GeographicalTree<./DSF/GeographicDestinationTree.rst>
  MealPlanList<./DSF/MealPlanList.rst>
  RoomList<./DSF/RoomList.rst>
  Category<./DSF/CategoryList.rst>
  StaticConfiguration<./DSF/StaticConfiguration.rst>
  RunTimeConfiguration<./DSF/RunTimeConfiguration.rst>
  ModifyValuation<./DSF/ModifyValuation.rst>
  ModifyReservation<./DSF/ModifyReservation.rst>
  MasterData<./DSF/MasterData.rst>
