.. highlight:: xml

#############
SOAP Examples
#############

Avail
-----

::

	<soapenv:Envelope xmlns:soapenv = 
	"http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns = 
	"http://schemas.xmltravelgate.com/hub/2012/06" xmlns:wsse = 
	"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
	  <soapenv:Header>
	    <wsse:Security>
	      <wsse:UsernameToken>
	        <wsse:Username>XXXXXX</wsse:Username>
	        <wsse:Password>XXXXXX</wsse:Password>
	      </wsse:UsernameToken>
	    </wsse:Security>
	  </soapenv:Header>
	  <soapenv:Body>
	    <ns:Avail>
	      <ns:availRQ>
	        <ns:timeoutMilliseconds>18000</ns:timeoutMilliseconds>
	        <ns:version>1</ns:version>
	        <ns:providerRQs>
	          <ns:ProviderRQ>
	            <ns:code>XXX</ns:code>
	            <ns:id>1</ns:id>
	            <ns:rqXML>
	              <AvailRQ>
	                <timeoutMilliseconds>99999</timeoutMilliseconds>
	                <source>
	                  <languageCode>en</languageCode>
	                </source>
	                <filterAuditData>
	                  <registerTransactions>false</registerTransactions>
	                </filterAuditData>
	                <Configuration>
	                  <User></User>
	                  <Password></Password>
	                  <UrlAvail>http://www.test.net/test_XML_V10.php?</UrlAvail>
	                  <UrlReservation>http://www.test.net/scr/reservation_xml.php</UrlReservation>
	                  <Parameters>
	                    <Parameter key = "UrlListHoteles" 
	                       value = "http://www.test.net/scr/searchxml/location.php?"></Parameter>
	                    <Parameter key = "UrlConsulta" 
	                       value = "https://www.test.net/scr/xml/travelgate.php?"></Parameter>
	                    <Parameter key = "office" value = "55555"></Parameter>
	                    <Parameter key = "password" value = "XXXXXX"></Parameter>
	                  </Parameters>
	                </Configuration>
	                <AvailDestinations>
	                  <Destination type = "CTY" code = "XXX"/>
	                </AvailDestinations>
	                <StartDate>08/08/2012</StartDate>
	                <EndDate>12/12/2012</EndDate>
	                <Currency>EUR</Currency>
	                <RoomCandidates>
	                  <RoomCandidate id = "1">
	                    <Paxes>
	                      <Pax age = "30" id = "1"/>
	                      <Pax age = "30" id = "2"/>
	                    </Paxes>
	                  </RoomCandidate>
	                </RoomCandidates>
	              </AvailRQ>
	            </ns:rqXML>
	          </ns:ProviderRQ>
	        </ns:providerRQs>
	      </ns:availRQ>
	    </ns:Avail>
	  </soapenv:Body>
	</soapenv:Envelope>

|

Multi Avail
-----------

::


	<soapenv:Envelope xmlns:soapenv = "http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns = "http://schemas.xmltravelgate.com/hub/2012/06" xmlns:wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
	  <soapenv:Header>
		<wsse:Security>
		  <wsse:UsernameToken>
			<wsse:Username>XXXXXX</wsse:Username>
	        <wsse:Password>XXXXXX</wsse:Password>
		  </wsse:UsernameToken>
		</wsse:Security>
	  </soapenv:Header>
	  <soapenv:Body>
		<ns:Avail>
		  <ns:availRQ>
			<ns:timeoutMilliseconds>18000</ns:timeoutMilliseconds>
			<ns:version>1</ns:version>
			<ns:providerRQs>
			  <ns:ProviderRQ>
				<ns:code>XXX</ns:code>
				<ns:id>1</ns:id>
				<ns:rqXML>
				  <AvailRQ>
					<timeoutMilliseconds>17700</timeoutMilliseconds>
					<source>
					  <languageCode>en</languageCode>
					</source>
					<filterAuditData>
					  <registerTransactions>false</registerTransactions>
					</filterAuditData>
					<Configuration>
	                  <User></User>
	                  <Password></Password>
	                  <UrlAvail>http://www.test.net/test_XML_V10.php?</UrlAvail>
	                  <UrlReservation>http://www.test.net/scr/reservation_xml.php</UrlReservation>
	                  <Parameters>
	                    <Parameter key = "UrlListHoteles" 
	                       value = "http://www.test.net/scr/searchxml/location.php?"></Parameter>
	                    <Parameter key = "UrlConsulta" 
	                       value = "https://www.test.net/scr/xml/travelgate.php?"></Parameter>
	                    <Parameter key = "office" value = "55555"></Parameter>
	                    <Parameter key = "password" value = "XXXXXX"></Parameter>
	                  </Parameters>
					</Configuration>
					<SearchType>Combined</SearchType>
					<CancellationPolicies>true</CancellationPolicies>
					<AvailDestinations>
					  <Destination type = "CTY" code = "1"/>
					</AvailDestinations>
					<StartDate>10/12/2014</StartDate>
					<EndDate>12/12/2014</EndDate>
					<Currency>EUR</Currency>
					<RoomCandidates>
					  <RoomCandidate id = "1">
						<Paxes>
						  <Pax age = "30" id = "1"/>
						  <Pax age = "30" id = "2"/>
						</Paxes>
					  </RoomCandidate>
					</RoomCandidates>
				  </AvailRQ>
				</ns:rqXML>
			  </ns:ProviderRQ>
			  <ns:ProviderRQ>
				<ns:code>XXX</ns:code>
				<ns:id>2</ns:id>
				<ns:rqXML>
				  <AvailRQ xmlns:xsi = "http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd = "http://www.w3.org/2001/XMLSchema">
					<timeoutMilliseconds>18000</timeoutMilliseconds>
					<source>
					  <languageCode>en</languageCode>
					</source>
					<filterAuditData>
					  <registerTransactions>false</registerTransactions>
					</filterAuditData>
					<Configuration>
	                  <User></User>
	                  <Password></Password>
	                  <UrlAvail>http://www.test.net/test_XML_V10.php?</UrlAvail>
	                  <UrlReservation>http://www.test.net/scr/reservation_xml.php</UrlReservation>
	                  <Parameters>
	                    <Parameter key = "UrlListHoteles" 
	                       value = "http://www.test.net/scr/searchxml/location.php?"></Parameter>
	                    <Parameter key = "UrlConsulta" 
	                       value = "https://www.test.net/scr/xml/travelgate.php?"></Parameter>
	                    <Parameter key = "office" value = "55555"></Parameter>
	                    <Parameter key = "password" value = "XXXXXX"></Parameter>
	                  </Parameters>
					</Configuration>
					<SearchType>Combined</SearchType>
					<CancellationPolicies>false</CancellationPolicies>
					<AvailDestinations>
					  <Destination type = "CTY" code = "2"/>
					</AvailDestinations>
					<StartDate>05/11/2014</StartDate>
					<EndDate>06/11/2014</EndDate>
					<Currency>EUR</Currency>
					<RoomCandidates>
					  <RoomCandidate cantidad = "1" id = "1">
						<Paxes>
						  <Pax age = "30" id = "1"/>
						  <Pax age = "30" id = "2"/>
						</Paxes>
					  </RoomCandidate>
					</RoomCandidates>
				  </AvailRQ>
				</ns:rqXML>
			  </ns:ProviderRQ>
			</ns:providerRQs>
		  </ns:availRQ>
		</ns:Avail>
	  </soapenv:Body>
	</soapenv:Envelope>

|
	
	
Valuation
---------

::

	<soapenv:Envelope xmlns:soapenv = 
	"http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns = 
	"http://schemas.xmltravelgate.com/hub/2012/06" xmlns:wsse = 
	"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
	  <soapenv:Header>
	    <wsse:Security>
	      <wsse:UsernameToken>
	        <wsse:Username>XXXXXX</wsse:Username>
	        <wsse:Password>XXXXXX</wsse:Password>
	      </wsse:UsernameToken>
	    </wsse:Security>
	  </soapenv:Header>
	  <soapenv:Body>
	    <ns:Valuation>
	      <ns:valuationRQ>
	        <ns:timeoutMilliseconds>180000</ns:timeoutMilliseconds>
	        <ns:version>1</ns:version>
	        <ns:providerRQ>
	          <ns:code>XXX</ns:code>
	          <ns:id>1</ns:id>
	          <ns:rqXML>
	            <ValuationRQ>
	              <timeoutMilliseconds>10000</timeoutMilliseconds>
	              <source>
	                <languageCode>en</languageCode>
	              </source>
	              <filterAuditData>
	                <registerTransactions>true</registerTransactions>
	              </filterAuditData>
	              <Configuration>
	                <User></User>
	                <Password></Password>
	                <UrlAvail>http://www.test.net/test_XML_V10.php?</UrlAvail>
	                <UrlReservation>http://www.test.net/scr/reservation_xml.php</UrlReservation>
	                <Parameters>
	                  <Parameter key = "UrlListHoteles" 
	                     value = "http://www.test.net/scr/searchxml/location.php?"></Parameter>
	                  <Parameter key = "UrlConsulta" 
	                     value = "https://www.test.net/scr/xml/travelgate.php?"></Parameter>
	                  <Parameter key = "office" value = "55555"></Parameter>
	                  <Parameter key = "password" value = "XXXXXX"></Parameter>
	                </Parameters>
	              </Configuration>
	              <StartDate>08/08/2014</StartDate>
	              <EndDate>07/11/2014</EndDate>
	              <MealPlanCode>AC</MealPlanCode>
	              <HotelCode>0001</HotelCode>
	              <PaymentType>MerchantPay</PaymentType>
	              <OptionType>Hotel</OptionType>
	              <Rooms>
	                <Room id = "91" roomCandidateRefId = "1" code = "91" 
	                description = "Standard Room"/>
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
	          </ns:rqXML>
	        </ns:providerRQ>
	      </ns:valuationRQ>
	    </ns:Valuation>
	  </soapenv:Body>
	</soapenv:Envelope>
	
|

GeographicalDestinationTree
---------------------------

::

	<soapenv:Envelope
		xmlns:soapenv = "http://schemas.xmlsoap.org/soap/envelope/"
		xmlns:ns = "http://schemas.xmltravelgate.com/hub/2012/06"
		xmlns:wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
		<soapenv:Header>
			<wsse:Security>
				<wsse:UsernameToken>
				  <wsse:Username>XXXXXX</wsse:Username>
				  <wsse:Password>XXXXXX</wsse:Password>
				</wsse:UsernameToken>
			</wsse:Security>
		</soapenv:Header>
	   <soapenv:Body>
		  <ns:GeographicDestinationTree>
			 <!--Optional:-->
			 <ns:geographicDestinationTreeRQ>
				<ns:timeoutMilliseconds>240000</ns:timeoutMilliseconds>
				<ns:version>1</ns:version>
				<ns:providerRQ>
				   <ns:code>XXX</ns:code>
				   <ns:id>1</ns:id>
				   <ns:rqXML>
		  <GeographicDestinationTreeRQ xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
	  <timeoutMilliseconds>999999</timeoutMilliseconds>
	  <source>
		<languageCode>en</languageCode>
	  </source>
	  <filterAuditData>
		<registerTransactions>true</registerTransactions>
	  </filterAuditData>
	  <Configuration>
		<User></User>
		<Password></Password>
		<UrlGeneric>http://test.Service</UrlGeneric>
		<Parameter key = "UrlListHoteles" 
			 value = "http://www.test.net/scr/searchxml/location.php?"></Parameter>
		  <Parameter key = "UrlConsulta" 
			 value = "https://www.test.net/scr/xml/travelgate.php?"></Parameter>
		  <Parameter key = "office" value = "55555"></Parameter>
		  <Parameter key = "password" value = "XXXXXX"></Parameter>
		</Parameters>
		</Configuration>
	</GeographicDestinationTreeRQ>
				   </ns:rqXML>
				</ns:providerRQ>
			 </ns:geographicDestinationTreeRQ>
		  </ns:GeographicDestinationTree>
	   </soapenv:Body>
	</soapenv:Envelope>
