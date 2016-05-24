.. highlight:: xml

###########################
Frequently Asked Questions
###########################

#. **How many suppliers can we request in one call?**

	Only one supplier per request. The only exception is using the Avail call, where you can use one or more suppliers.

#. **How can I identify which suppliers is which in the Avail call?**

	By using the field ID in the request.

	For example:


	**In the request:**

	::

	<!--First supplier-->               <!--Second supplier-->
	<ns:code>TEST</ns:code>             <ns:code>TEST2</ns:code>
	<ns:id>1</ns:id>                    <ns:id>2</ns:id>

	**In the response:**

	::

	<!--Response first supplier-->       <!--Response Second supplier-->
	<refId>1</refId>                     <refId>2</refId>


#. **How does the price work and how should I interpret the value in the field "commission"?**


Every option has a price and every price indicates the currency, the amount, if it is binding and the commission.

* *Binding:*

If binding is set as true, then the client cannot sell the product provided by the supplier for a lower price. If it's set
as false, the client can sell the product for a lower price.

* *Commission:*


	-  If commission = 0 then the price returned is a net price, and the
	   supplier is disclosing that the commission **must** be 0.

	-  If commission = -1 then the supplier is not disclosing the sale price
	   or if the price is net. This information is obtained when signing with the
	   supplier or also if the binding price is true/false.

	-  When commission is greater than 0, for example: commission = 12, it
	   is a sale price, and this commission is informed for the supplier
	   ( this price is mandatory if binding price is true ).


|



#. **What is a static download and why do we use it?**

    There are times when you want to do a call of your information on-line,
    but this call can take more that 5 minutes, so, how can we do this quicker?
    We will download all of your information necessary to our servers,
    so when this happens, we can send you the static information
    that we have loaded into our system.



#. **In the tag "RequiredAllPassenger", is specifying the names of the babies necessary?**

    If the value of "RequiredAllPassengers" is true in the static data, then yes,
    it is necessary
