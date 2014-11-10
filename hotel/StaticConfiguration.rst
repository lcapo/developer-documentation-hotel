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

|

*Detailled* Description
-----------------------


* <MaxNumberHotels>25</MaxNumberHotels>:
	
-Maximum number of hotel that can be requested in a avail petition.

|
  
*  <MaxNumberCities>100</MaxNumberCities>:

-Maximum number of cities that can be requested in a avail petition.

|
	
*  <MaxNumberZones>100</MaxNumberZones>:

-Maximum number of zones that can be requested in a avail petition.

|
	
*  <MaxNumberGeoCodes>25</MaxNumberGeoCodes>:

-Maximum number of GeoCodes that can be requested in a avail petition.

|
	
*  <RequiredRoomList>false</RequiredRoomList>:
  
-The provider has implemented a list of rooms, siempre y cuando el proveedor devuelva la descripcion de habitacion en disponiblidiad, esta llamada no sera obligatoria.

|
	
*  <InformCancelPolicies>true</InformCancelPolicies>:

-The provider informs of the cancellation policies.

|
	
*  <InformBindingPriceValuation>false</InformBindingPriceValuation>:

-Informs if the price of the option in the response of valuation is binding.

|
	
*  <InformBindingPrice>false</InformBindingPrice>:

-Provider returns binding PVPs in availability.

|
	
*  <InformNRFValuation>true</InformNRFValuation>:
  
-The provider can inform in valuation if the rate is non-refundable.

|
	
*  <InformNRFRate>true</InformNRFRate>:

-The provider can inform in availability if the rate is non-refundable.

|
	
*  <Inform55Rate>false</Inform55Rate>:
  
-The provider informs the options with rates of pax of 55 years old or over in availability.

|
	
*  <InformPackageRate>false</InformPackageRate>:

-The provider informs the options with package rates in availability. These options cant be sold by seperate, need to add a service (like a plane ticket) 


|
	
*  <InformExtraActivity>false</InformExtraActivity>:

-The provider informs of the possible option type Hotel+entrance.

|
	
*  <InformForfait>false</InformForfait>:

-The provider informs of the possible option type Hotel+Forfait.

|
	
*  <RemarksValuation>true</RemarksValuation>:
  
-The provider informs of the important observation in policies, like per example, supplies paid in the hotel.

|
	
*  <MaxNumberRoomCandidates>3</MaxNumberRoomCandidates>:

-Maximum number of room candidates that can be requested in the same avail request.

|
	
*  <MaxPaxInRoomCandidates>3</MaxPaxInRoomCandidates>:

-Maximum number paxs in same room that can be requested in the same avail request.

|
	
*  <Release>0</Release>:

-Minimum days that is required in between booking date and checking date ( days in advance ). If the value is cero there is no limitation.

|
	
*  <MinimumStay>0</MinimumStay>:

-Minimum number of days that need to be booked. If the value is cero there is no limitation.

|
	
*  <InformBillingSupplierReservation>false</InformBillingSupplierReservation>:

-Informs of the data of the external provider in the booking.

|
	
*  <ImplementsProvideLocatorReservationRead>true</ImplementsProvideLocatorReservationRead>:
  
-The provider implements the consult transaction with the **provider** localizator.

|
	
*  <ImplementsClientLocatorReservationRead>false</ImplementsClientLocatorReservationRead>:

-The provider implements the consult transaction with the **client** localizator.

|
	
*  <ImplementsCancel>true</ImplementsCancel>:

-The provider implements cancellation transaction.

|
	
*  <InformPriceReservation>false</InformPriceReservation>:
  
-The provider informs about the price in the reservation in the booking RS.

|
	
*  <HotelListLanguages>

-Languages that the provider can return their information.

<Languages>

<Language>en</Language>

<Language>es</Language>

<Language>de</Language>

<Language>fr</Language>

<Language>it</Language>

</Languages>

</HotelListLanguages>

|
  
 
*  <ReservationListCreationDate>true</ReservationListCreationDate>:

-The provider implements the list of bookings transaction by creation date.

|
	
*  <ReservationListCheckDate>true</ReservationListCheckDate>:

-The provider implements the list of bookings transaction by checking date.

|
  
  
*  <InformCancelPoliciesReservationRead>false</InformCancelPoliciesReservationRead>
 
-Informs of the cancellation policies in the booking consultation.

|
  
*  <InformCancelPoliciesReservationList>false</InformCancelPoliciesReservationList>:
  
-Informs of the cancellation policies in the booking list.

|
  
*  <InformCancelPoliciesAvail>false</InformCancelPoliciesAvail>:

-Informs of the cancellation policies in availability.

|
  
*  <InformChangesPolicies>false</InformChangesPolicies>:

-The provider informs if there is an extra fee for any booking modification.

|
  
*  <ImplementsDeltaPrice>false</ImplementsDeltaPrice>:

-Implemented a margin stipulated by the client for booking with a higher price (delta). 

|
  
*  <RequiredAllPassengers>true</RequiredAllPassengers>:

-Needs all of the data (names and surnames) of all the pax in booking. 

|
   
*  <ImplementsDailyPrice>false</ImplementsDailyPrice>:

-Price disaggregated per days.

|
  
*  <ImplementsOffersAvail>false</ImplementsOffersAvail>:

-If it shows in availability the applied offers. 

|
  
*  <ImplementsRemarksAvail>false</ImplementsRemarksAvail>:

-Observation and comments. 

|
  
