.. highlight:: xml

###########################
Frequently Asked Questions! 
###########################

#. **How many providers can we do a one request?**

	Only one provider per request. The only exception is with the petition MultiAvail, where you can use one or more providers. 

#. **How can I identify which providers is which in the MultiAvail call?**

	By using the field ID in the request. 
	
	For example:
	
	
	**In the request:**
	
	::

	<!--First provider-->               <!--Second provider-->
	<ns:code>TEST</ns:code>             <ns:code>TEST2</ns:code>
	<ns:id>1</ns:id>                    <ns:id>2</ns:id>
	
	**In the response:**
	
	::
	
	<!--Response first provider-->       <!--Response Second provider-->
	<refId>1</refId>                     <refId>2</refId>
	

#. **How does the price work and how should I interpret the value in the field "commission"?**

    You can find the answer to this question in the Hotel API in the "Avail" section under the paragraph "remarks":
    
    http://docs.xmltravelgate.com/en/latest/hotel/DSF/Avail.html



#. **What is a static download and why do we use it?**

    There are times when you want to do a call of your information on-line, 
    but this call can take more that 5 minutes, so, how can we do this quicker?
    We will download all of your information necessary to our servers,
    so when this happens, we can send you the static information
    that we have loaded in our system.



#. **In the tag "RequiredAllPassenger", is specifying the names of the babies necessary?**

    If the value of "RequiredAllPassengers" is true in the static data, then yes,
    it is necessary
