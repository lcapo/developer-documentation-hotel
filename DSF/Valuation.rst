.. highlight:: xml

Valuation
=========

|

Method Goals
------------

This method aims to return the total price and cancel policies of 
the selected *Option*. This *Option* **must** be selected in the 
previous step (*Avail*).

|

Request Format
--------------

The *Valuation* request is same that availabilityRQ and add rooms and Mealplan code.

|

Response Format
---------------

The returned XML contains the total price and list of cancel policies. 
Sometimes this method will fail since the selected option at *Avail* 
time will not be available in this stage. In this case the integration 
returns one of our errors: code 301. For more information of our errors, 
please consult the paragraph "Lists of Data" 

|

Remarks
-------

The maximum time, that is permitted in our system, before the connection is closed,  is of **180000** milliseconds.

|

ValuationRQ Example
-------------------

::

	<ValuationRQ>
		<StartDate>28/01/2014</StartDate>
		<EndDate>29/01/2014</EndDate>
		<OnRequest>false</OnRequest>
		<MealPlanCode>D</MealPlanCode>
		<HotelCode>10</HotelCode>
		<PaymentType>MerchantPay</PaymentType>
		<OptionType>Hotel</OptionType>
		<BlockOption>true</BlockOption>
		<Nationality>ES</Nationality>			
		<Rooms>
			<Room id = "4582" roomCandidateRefId = "1" code = "506"	description = "Doble Standard.."/>
		</Rooms>
		<RoomCandidates>
			<RoomCandidate id = "1">
				<Paxes>
					<Pax age = "30" id = "1"/>
					<Pax age = "30" id = "2"/>
				</Paxes>
			</RoomCandidate>
		</RoomCandidates>
	</ValuationRQ>




ValuationRQ Description
-----------------------

+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| Element                                  | Number   | Type      | Description                                                             |
+==========================================+==========+===========+=========================================================================+
| ValuationRQ                              | 1        |           | Root node.                                                              |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| StartDate                                | 1        | String    | Start date to search rates.                                             |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| EndDate                                  | 1        | String    | End date to search rates.                                               |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| OnRequest                                | 1        | Boolean   | Indicates if you want to receive the on request options in AvailRS, as  |
|                                          |          |           | long as the provider returns it in this call (see StaticConfiguration). |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| BlockOption                              | 1        | Boolean   | Indicates if you want to block the option selected in AvailRS, as       |
|                                          |          |           | long as the provider allow it in this call (see StaticConfiguration).   |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| MealPlanCode                             | 1        | String    | MealPlan code.                                                          |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| HotelCode                                | 1        | String    | Hotel code.                                                             |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| PaymentType                              | 1        | String    | Indicates the typology of payment.                                      |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| OptionType                               | 1        | String    | Indicates the type of option.                                           |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| Nationality                              | 0..1     | String    | Nationality of the Holder (use ISO3166_1_alfa_2). This informations     |
|                                          |          |           | will be mandatory depending on the provider, as long as the provider    |
|                                          |          |           | returns it in this call (see StaticConfiguration).                      |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| Rooms                                    | 1        |           | Rooms of this option ( room list).                                      |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| Rooms/Room                               | 1..n     |           | Detail of room.                                                         |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| *@id*                                    | 1        | String    | Identifier of the room.                                                 |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| *@roomCandidateRefId*                    | 1        | Integer   | Identifier of room candidate.                                           |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| *@code*                                  | 1        | String    | Room code.                                                              |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| *@description*                           | 1        | String    | Room description.                                                       |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| RoomCandidates                           | 1        |           | Rooms required.                                                         |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| RoomCandidates/RoomCandidate             | 1..n     |           | Room required.                                                          |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| *@id*                                    | 1        | Integer   | Id of the requested room (starting at 1).                               |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| RoomCandidates/RoomCandidate/Paxes/Pax   | 1..n     |           | Pax required.                                                           |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| *@age*                                   | 1        | Integer   | Passenger age.                                                          |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| *@id*                                    | 1        | Integer   | Passenger id (starting at 1).                                           |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| Parameters                               | 0..1     |           | Additional parameters that have been reported in the option (AvailRS)   |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| Parameters/Parameter                     | 0..n     |           | Additional parameter that requires the integration                      |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| *@key*                                   | 1        | String    | Contains the keyword/Id to identify a parameter.                        |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+
| *@value*                                 | 1        | String    | Contains the value of the parameter                                     |
+------------------------------------------+----------+-----------+-------------------------------------------------------------------------+

|

ValuationRS Example
-------------------

::

	<ValuationRS>
		<Parameters>
			<Parameter key = "bd1" value = "43"/>
		</Parameters>
		<Status>OK</Status>
		<Price currency = "EUR" amount = "36.20" binding = "false" commission = "-1"/>
		<CancelPenalties nonRefundable = "false">
			<CancelPenalty>
				<HoursBefore>48</HoursBefore>
				<Penalty type = "Importe" currency = "EUR">72.40</Penalty>
			</CancelPenalty>
		</CancelPenalties>
		<Fees>
			<Fee includedPriceOption = "true" description = "TaxAndServiceFee">
				<Price currency = "EUR" amount = "8.11" binding = "false" commission = "-1"/>
			</Fee>
		</Fees>
		<Remarks/>
		<PaymentOptions cash="false" bankAcct="false">
			<Cards>
				<Card code="VI"/>
				<Card code="AX"/>
				<Card code="CA"/>  
			</Cards> 
		<PaymentOptions/>		
	   <CancelPoliciesDescription/>
	</ValuationRS>

|

ValuationRS Description
-----------------------

+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Element                                                                         | Number   | Type      | Description                                                                                                                                                                                                       |
+=================================================================================+==========+===========+===================================================================================================================================================================================================================+
| ValuationRS                                                                     | 1        |           | Root node.                                                                                                                                                                                                        |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Parameters                                                                      | 0..1     |           | Parameters for additional information.                                                                                                                                                                            |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Parameters/Parameter                                                            | 1..n     |           | List of parameter.                                                                                                                                                                                                |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@key*                                                                          | 1        | String    | Contains the keyword/Id to identify a parameter.                                                                                                                                                                  |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@value*                                                                        | 1        | String    | Contains the value of the parameter.                                                                                                                                                                              |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Status                                                                          | 1        |           | Status option (OK = available, RQ = on request).                                                                                                                                                                  |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Price                                                                           | 1        |           | Total price of this valuation.                                                                                                                                                                                    |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@currency*                                                                     | 1        | String    | Currency code.                                                                                                                                                                                                    |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@amount*                                                                       | 1        | Decimal   | Option Amount.                                                                                                                                                                                                    |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@binding*                                                                      | 1        | Boolean   | Identifies if is the price is binding ( When true the sale price returned **must** not be less than the price informed.                                                                                           |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@commission*                                                                   | 1        | Decimal   | Commission ( -1 = not specified (will come indicated with the provider contract ), 0 = net price, X = % of the commission that applies to the amount.                                                             |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| CancelPenalties                                                                 | 1        |           | Information of cancellation policies.                                                                                                                                                                             |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@nonRefundable*                                                                | 1        | Boolean   | Indicate if this option is nonRefundable (true or false).                                                                                                                                                         |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| CancelPenalties/CancelPenalty                                                   | 0..n     |           | Listing cancellation penalties.                                                                                                                                                                                   |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| CancelPenalties/CancelPenalty/HoursBefore                                       | 1        | String    | Number of hours prior to arrival day in which this Cancellation policy applies .                                                                                                                                  |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| CancelPenalties/CancelPenalty/Penalty                                           | 1        |           | Contains the value to apply.                                                                                                                                                                                      |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@type*                                                                         | 1        | String    | Type of penalty Possible values: "Noches" (nights) , "Porcentaje" (percentage) ,"Importe" (price value).                                                                                                          |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@currency*                                                                     | 1        | String    | Currency code.                                                                                                                                                                                                    |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Remarks                                                                         | 0..1     | String    | Remarks.                                                                                                                                                                                                          |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| PaymentOptions                                                                  | 0..1     | String    | Type of cards allowed by the provider. This tag only is mandatory if payment type is different that *MerchantPay*.                                                                                                |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@cash*                                                                         | 1        | Boolean   | Deprecated attribute.                                                                                                                                                                                             |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@bankAcct*                                                                     | 1        | Boolean   | Deprecated attribute.                                                                                                                                                                                             |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| PaymentOptions/Cards                                                            | 1        |           | List of cards allowed.                                                                                                                                                                                            |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| PaymentOptions/Cards/Card                                                       | 1..n     |           | Type card allowed.                                                                                                                                                                                                |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@code*                                                                         | 1        | String    | Code card. See in CardInfo the possible values, provided in Detailed Description (VI,AX,BV,CA...)                                                                                                                 |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Fees                                                                            | 0..1     |           | Contains a list of fees.                                                                                                                                                                                          |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Fees/Fee                                                                        | 1 ..n    |           | Contains details of the fee.                                                                                                                                                                                      |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@includedPriceOption*                                                          | 1        | Boolean   | Indicates if the price of the fee is included or not in **the final price** (value indicated in the node Price in ValuationRS).                                                                                   |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@description*                                                                  | 1        | String    | Remarks of the fee.                                                                                                                                                                                               |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Fees/Fee/Price                                                                  | 1        |           | Contains the price of the fee.                                                                                                                                                                                    |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@currency*                                                                     | 1        | String    | Currency code.                                                                                                                                                                                                    |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@amount*                                                                       | 1        | Decimal   | Fee Amount.                                                                                                                                                                                                       |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@binding*                                                                      | 1        | Boolean   | Identifies if is the price is binding ( When true the sale price returned **must** not be less than the price informed.                                                                                           |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *@commission*                                                                   | 1        | Decimal   | Commission ( -1 = not specified (will come indicated with the provider contract ), 0 = net price, X = % of the commission that applies to the amount.                                                             |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| CancelPoliciesDescription                                                       | 0..1     | String    | Contains the cancellation penalties in free text.                                                                                                                                                                 |
+---------------------------------------------------------------------------------+----------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

|

Detailed Description
--------------------

**Providers with allotment blockage**

There are some providers which, for their internal reasons, block the allotments of the petitions. If this should be the case, the clients have to relaunch automatically the valuation, provided that
it has past more than 30 minutes of the last valuation petition. 

Given the case, that a provider has a specific transaction for blocking allotments ( normally called pre-confirmation, quote, booking with a parameter quote.. ), then there is two possible paths that you need to follow:

* If the provider assures a blockage equal or superior to 30 minutes then you will have to do the blockage of allotment petition.

* If the provider doesn't assure a blockage superior of 30 minutes then the petition of blockage of allotment will have to be done in the booking petition.

|

**Status:**

The valuation response depends the parameter <OnRequest> set:
In case that the parameter <OnRequest> is set as false, the integration filter this options if the supplier provide us the new status with value on request in ValuationRS, then we return an error because the provider change the status option.
In case that the parameter <OnRequest> is set as true, we don't filter the option.

| 

**CardInfo:**


+-------+--------------------------+
| Codes | Names                    |
+=======+==========================+
| VI    | Visa                     |
+-------+--------------------------+
| AX    | American Express         |
+-------+--------------------------+
| BC    | BC Card                  |
+-------+--------------------------+
| CA    | MasterCard               |
+-------+--------------------------+
| CB    | Carte Blanche            |
+-------+--------------------------+
| CU    | China Union Pay          |
+-------+--------------------------+
| DS    | Discover                 |
+-------+--------------------------+
| DC    | Diners Club              |
+-------+--------------------------+
| T     | Carta Si                 |
+-------+--------------------------+
| R     | Carte Bleue              |
+-------+--------------------------+
| N     | Dankort                  |
+-------+--------------------------+
| L     | Delta                    |
+-------+--------------------------+
| E     | Electron                 |
+-------+--------------------------+
| JC    | Japan Credit Bureau      |
+-------+--------------------------+
| TO    | Maestro                  |
+-------+--------------------------+
| S     | Switch                   |
+-------+--------------------------+
| EC    | Electronic Cash          |
+-------+--------------------------+
| EU    | EuroCard                 |
+-------+--------------------------+
| TP    | universal air travel card|
+-------+--------------------------+
| OP    | optima                   |
+-------+--------------------------+
| ER    | Air Canada/RnRoute       |
+-------+--------------------------+
| XS    | access                   |
+-------+--------------------------+
| O     | others                   |
+-------+--------------------------+

|

**CancelPenalty:**

The penalty in cancelling a booking depends on which situation you do the cancellation. 
The factors that affects the cancel penalization goes as follows:
 
* **HoursBefore:** Number of hours until the checking date. This time is calculated based on the local time of destination.

* **Type:** There are three values that can be inside types: 

 * *Noches:* Which will indicate the number of nights which will be penalized.
	
 * *Porcentaje:* Which indicates the percentage to pay based on the option price.
	
 * *Importe:* That indicates the exact amount that it is necessary to pay.

* **Currency:** Money currency of the import.

|

**Note:**

Keep the parameters in the avail response to include them in the valuation request.

Keep the parameters in the valuation response to include them in the reservation request.

|
