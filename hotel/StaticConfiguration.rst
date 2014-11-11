StaticConfiguration
===================

**Method Goals**

|

This message provides information about the static configuration of
the provider, to see and configure the provider in the best way.

|

**Request Format**

|

The request does not require any elements empty request.

|

**Response Format**

|

The XML returned contains more elements on the configuration (number
of hotels, the number of cities and the number of areas of availability,
if the provider returns the cancellation policies, maximum number of
distributions, maximum number of paxes in a distribution, release days,
stay minimum, list of languages that allows ....).

|

*StaticConfigurationRQ* Example
-------------------------------

::

    <StaticConfigurationRQ>
    </StaticConfigurationRQ>

|

*StaticConfigurationRQ* Description
-----------------------------------

+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Element              | Number   | Type     | Description                                                                                 |
+======================+==========+==========+=============================================================================================+
| StaticConfigurationRQ| 1        |          | Root node.                                                                                  |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+

|

*StaticConfigurationRS* Example
-------------------------------

::

    <StaticConfigurationRS>
        <MaxNumberHotels>2000</MaxNumberHotels>
        <MaxNumberCities>1</MaxNumberCities>
        <MaxNumberZones>1</MaxNumberZones>
        <MaxNumberGeoCodes>0</MaxNumberGeoCodes>
        <RequiredRoomList>false</RequiredRoomList>
        <InformCancelPolicies>true</InformCancelPolicies>
        <InformBindingPriceValuation>true</InformBindingPriceValuation>
        <InformBindingPrice>true</InformBindingPrice>
        <InformNRFValuation>true</InformNRFValuation>
        <InformNRFRate>true</InformNRFRate>
        <Inform55Rate>true</Inform55Rate>
        <InformPackageRate>true</InformPackageRate>
        <InformExtraActivity>false</InformExtraActivity>
        <InformForfait>true</InformForfait>
        <RemarksValuation>true</RemarksValuation>
        <MaxNumberRoomCandidates>9</MaxNumberRoomCandidates>
        <MaxPaxInRoomCandidates>9</MaxPaxInRoomCandidates>
        <Release>0</Release>
        <MinimumStay>0</MinimumStay>
        <InformBillingSupplierReservation>false</InformBillingSupplierReservation>
        <ImplementsProvideLocatorReservationRead>true</ImplementsProvideLocatorReservationRead>
        <ImplementsClientLocatorReservationRead>true</ImplementsClientLocatorReservationRead>
        <ImplementsCancel>true</ImplementsCancel>
        <InformPriceReservation>true</InformPriceReservation>
        <HotelListLanguages>
            <Languages>
                <Language>en</Language>
                <Language>es</Language>
                <Language>de</Language>
                <Language>pt</Language>
                <Language>fr</Language>
                <Language>it</Language>
            </Languages>
        </HotelListLanguages>
        <ReservationListCreationDate>true</ReservationListCreationDate>
        <ReservationListCheckDate>true</ReservationListCheckDate>
        <HotelListType>OffLineCompleted</HotelListType>
        <DescriptiveInfoType>NotImplemented</DescriptiveInfoType>
        <GeographicDestinationTreeType>OffLine</GeographicDestinationTreeType>
        <AvailDestinationTreeType>OffLine</AvailDestinationTreeType>
        <ListadoServicios>OnLine</ListadoServicios>
        <RoomListType>OnLine</RoomListType>
        <DescriptiveInfoParallelism>-1</DescriptiveInfoParallelism>
        <InformCancelPoliciesReservationRead>false</InformCancelPoliciesReservationRead>
        <InformCancelPoliciesReservationList>false</InformCancelPoliciesReservationList>
        <InformCancelPoliciesAvail>false</InformCancelPoliciesAvail>
        <InformChangesPolicies>false</InformChangesPolicies>
        <ImplementsDeltaPrice>false</ImplementsDeltaPrice>
        <RequiredAllPassengers>true</RequiredAllPassengers>
        <InformBedsAvail>false</InformBedsAvail>
        <ModifyTransactions>
            <ModifyTransaction>
                <Modify>ModifyStartDateAddDays</Modify>
                <Modify>ModifyEndDateAddDays</Modify>
            </ModifyTransaction>
            <ModifyTransaction>
                <Modify>ModifyHolder</Modify>
                <Modify>ModifyRoomsAddRooms</Modify>
                <Modify>ModifyRoomsRemoveRooms</Modify>
            </ModifyTransaction>
        </ModifyTransactions>
    </StaticConfigurationRS>

|

*StaticConfigurationRS* Description
-----------------------------------


+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Element              | Number   | Type     | Description                                                                                 |
+======================+==========+==========+=============================================================================================+
| StaticConfigurationRS| 1        |          | Root node.                                                                                  |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| MaxNumberHotels      | 1        | Integer  | Maximum number of hotel that can be requested in a avail petition.                          |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| MaxNumberCities      | 1        | Integer  | Maximum number of cities that can be requested in a avail petition.                         |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| MaxNumberZones       | 1        | Integer  | Maximum number of zones that can be requested in a avail petition.                          |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| MaxNumberGeoCodes    | 1        | Integer  | Maximum number of GeoCodes that can be requested in a avail petition.                       |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| RequiredRoomList     | 1        | Boolean  | The provider has implemented a list of rooms, where the provider will return the description|
|                      |          |          | of the room in availability, not a mandatory call.                                          |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformCancelPolicies | 1        | Boolean  | The provider informs of the cancellation policies.                                          |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformBinding        | 1        | Boolean  | Informs if the price of the option in the response of valuation is binding.                 |
| PriceValuation       |          |          |                                                                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformBindingPrice   | 1        | Boolean  | Provider returns binding PVPs in availability.                                              |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformNRFValuation   | 1        | Boolean  | The provider can inform in valuation if the rate is non-refundable.                         |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformNRFRate        | 1        | Boolean  | The provider can inform in availability if the rate is non-refundable.                      |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Inform55Rate         | 1        | Boolean  | The provider informs the options with rates of pax of 55 years old or over in availability. |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformPackageRate    | 1        | Boolean  | The provider informs the options with package rates in availability. These options cant be  |
|                      |          |          | sold by separate, need to add a service (like a plane ticket).                              |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformExtraActivity  | 1        | Boolean  | The provider informs of the possible option type Hotel+entrance.                            |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformForfait        | 1        | Boolean  | The provider informs of the possible option type Hotel+Forfait.                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| RemarksValuation     | 1        | Boolean  | The provider informs of the important observation in policies, like per example,            |
|                      |          |          | supplies paid in the hotel.                                                                 |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| MaxNumberRoom        | 1        | Integer  | Maximum number of room candidates that can be requested in the same avail request.          |
| Candidates           |          |          |                                                                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| MaxPaxInRoom         | 1        | Integer  | Maximum number paxs in same room that can be requested in the same avail request.           | 
| Candidates           |          |          |                                                                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Release              | 1        | Integer  | Minimum days that is required in between booking date and checking date ( days in advance ).|
|                      |          |          | If the value is zero then there is no limitation.                                           |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| MinimumStay          | 1        | Integer  | Minimum number of days that are needed to be booked. If the value is zero then there is     |
|                      |          |          | no limitation.                                                                              | 
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformBilling        | 1        | Boolean  | Informs of the data of the external provider in the booking.                                |
| SupplierReservation  |          |          |                                                                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| ImplementsProvide    | 1        | Boolean  | The provider implements the consult transaction with the **provider** localizator.          |
| LocatorReservation   |          |          |                                                                                             |
| Read                 |          |          |                                                                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| ImplementsClient     | 1        | Boolean  | The provider implements the consult transaction with the **client** localizator.            |
| LocatorReservation   |          |          |                                                                                             |
| Read                 |          |          |                                                                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| ImplementsCancel     | 1        | Boolean  | The provider implements cancellation transaction.                                           |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformPrice          | 1        | Boolean  | The provider informs about the price in the reservation in the booking RS.                  |
| Reservation          |          |          |                                                                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| HotelListLanguages   | 1        | Boolean  | Languages that the provider can return their information.                                   |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| ReservationList      | 1        | Boolean  | The provider implements the list of bookings transaction by creation date.                  |
| CreationDate         |          |          |                                                                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| ReservationList      | 1        | Boolean  | The provider implements the list of bookings transaction by checking date.                  |
| CheckDate            |          |          |                                                                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformCancelPolicies | 1        | Boolean  | Informs of the cancellation policies in the booking consultation.                           |
| ReservationRead      |          |          |                                                                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformCancelPolicies | 1        | Boolean  | Informs of the cancellation policies in the booking list.                                   |
| ReservationList      |          |          |                                                                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformCancel         | 1        | Boolean  | Informs of the cancellation policies in availability.                                       |
| PoliciesAvail        |          |          |                                                                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| InformChangesPolicies| 1        | Boolean  | The provider informs if there is an extra fee for any booking modification.                 |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| ImplementsDeltaPrice | 1        | Boolean  | Implemented a margin stipulated by the client for booking with a higher price (delta).      |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| RequiredAllPassengers| 1        | Boolean  | Needs all of the data (names and surnames) of all the pax in booking.                       |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| ImplementsDailyPrice | 1        | Boolean  | Price disaggregated per days.                                                               |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| ImplementsOffersAvail| 1        | Boolean  | If it shows in availability the applied offers.                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+
| Implements           | 1        | Boolean  | Observation and comments.                                                                   |
| RemarksAvail         |          |          |                                                                                             |
+----------------------+----------+----------+---------------------------------------------------------------------------------------------+



|

