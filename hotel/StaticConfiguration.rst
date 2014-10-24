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
