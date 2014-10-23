Common Elements
===============
This node will be in every request and response objects. 

The request objects contains the provider's configuration, urls and credentials.

The response object contains the operation status and errors if any.

|

*Common Element*s RQ Example
----------------------------

::

    :rubric:<HotelBaseRQ>
        <echoToken>TEST</echoToken>
        <timeoutMilliseconds>20000</timeoutMilliseconds>
        <source>
            <agencyCode>XXXX</agencyCode>
            <languageCode>es</languageCode>
        </source>
        <filterAuditData>
            <registerTransactions>True</registerTransactions>
        </filterAuditData>
        <Configuration>
            <User>USERXX</User>
            <Password>PWXX</Password>
            <UrlAvail>www.proveedor.es/avail</UrlAvail>
            <UrlReservation>www.proveedor.es/reservation</UrlReservation>
            <UrlValuation>www.proveedor.es/valuation</UrlValuation>
            <UrlGeneric>www.proveedor.es</UrlGeneric>
            <Parameters>
                <Parameter key = "SegundoPW" value = "PWXML"/>
            </Parameters>
        </Configuration>
        …
    </HotelBaseRQ>

| 

*Common Elements* RQ Description
--------------------------------



+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| Element                                | Number   | Type      | Description                                                          |
+========================================+==========+===========+======================================================================+
| HotelBaseRQ                            | 1        |           | Root node.                                                           |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| echoToken                              | 0..1     | String    | Echo token to be returned in response (valid for test purposes).     |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| timeoutMillisencods                    | 1        | Integer   | Timeout in milliseconds that client will be waiting that response.   |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| source                                 | 1        |           | Information about source requesting the operation.                   |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| source/agencyCode                      | 0..1     | String    | Agency code that requests the operation.                             |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| source/languageCode                    | 1        | String    | Language code (ISO 3166-1 alpha-2) format.                           |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| filterAuditData                        | 1        |           | Enables or disables information returned in audit data.              |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| filterAuditData/registerTransactions   | 1        | Boolean   | Returns all the transactions (XMLs) exchanged with the provider.     |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| Configuration                          | 1        |           | Information about source requesting the operation.                   |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| Configuration/User                     | 0..1     | String    | User code for connection.                                            |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| Configuration/Password                 | 0..1     | String    | Password for the connection.                                         |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| Configuration/UrlGeneric               | 0..1     | String    | Url generic connection.                                              |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| Configuration/UrlAvail                 | 0..1     | String    | Url for Avail method.                                                |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| Configuration/UrlValuation             | 0..1     | String    | Url for Valuation method.                                            |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| Configuration/UrlReservation           | 0..1     | String    | Url for Reservation method.                                          |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| Configuration/Parameters               | 0..1     |           | Parameters for additional information.                               |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| Configuration/Parameters/Parameter     | 0..n     |           | List of parameter.                                                   |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| *@key*                                 | 1        | String    | Contains the keyword/Id to identify a parameter.                     |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+
| *@value*                               | 1        | String    | Contains the value of the parameter                                  |
+----------------------------------------+----------+-----------+----------------------------------------------------------------------+

| 

*Common Elements RS* Example
----------------------------

::

    <HotelBaseRS>
        <echoToken>TEST</echoToken>
        <OperationImplemented>true</OperationImplemented>
        <applicationErrors>
            <type>102</type>
            <code>xxx</code>
            <description>xxx</description>
        </applicationErrors>
        …
        <auditData>
            <transactions>
                <timeStamp>2011-10-6T15:19:45.3544495+02:00</timeStamp>
                <RQ/>
                <RS/>
            </transactions>
            …
            <timeStamp>2011-10-26T15:19:43.4014745+02:00</timeStamp>
            <processTimeMilliseconds>19532</processTimeMilliseconds>
        </auditData>
        …
    </HotelBaseRS>

| 

*Common Elements RS Description*
--------------------------------



+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| Element                             | Number   | Type      | Description                                                        |
+=====================================+==========+===========+====================================================================+
| HotelBaseRS                         | 1        |           | Root node.                                                         |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| echoToken                           | 0..1     | String    | Echo token to be returned in response (valid for test purposes).   |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| OperationImplemented                | 1        | Boolean   | If the operation is implemented by this provider or not.           |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| applicationErrors                   | 0..n     |           | Application errors reported by provider.                           |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| applicationErrors/type              | 1        | String    | Error Type as specified by XML Travelgate.                         |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| applicationErrors/code              | 1        | String    | Native error code reported by provider.                            |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| applicationErrors/description       | 1        | String    | Error description.                                                 |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| auditData                           | 1        |           | Information about processing that transaction.                     |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| auditData/transactions              | 0..n     |           | List of transactions communicated with provider.                   |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| auditData/transactions/timeStamp    | 1        | Integer   | TimeStamp in which has been generated that transaction.            |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| auditData/transactions/RQ           | 1        | String    | Transaction Request.                                               |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| auditData/transactions/RS           | 1        | String    | Transaction Response.                                              |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| auditData/timeStamp                 | 1        | Integer   | imeStamp in which response has been generated                      |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+
| auditData/processTimeMilliseconds   | 1        | Integer   | Time in milliseconds consumed by this method.                      |
+-------------------------------------+----------+-----------+--------------------------------------------------------------------+

|