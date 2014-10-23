*DescriptiveInfo* (Hotel Details)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Method Goals

| 
| This method returns the details of a hotel (pictures, descriptions
...) for a given language.

Request Format

| 
| The request just requires the hotel code and language code (ISO-639-1)
( this is specified within the source-->languageCode).

Response Format

| 
| The result returns the details of that hotel.

Remarks

| 
| The languages codes are limited by each provider.
| `toc <#toc>`__

--------------

*DescriptiveInfoRQ* Example
'''''''''''''''''''''''''''

::

    <DescriptiveInfoRQ>
        <Hotel>
            <Code>524AC</Code>
        </Hotel>
    </DescriptiveInfoRQ>

| 
| `toc <#toc>`__

--------------

*DescriptiveInfoRQ* Description
'''''''''''''''''''''''''''''''

Element

Number

Type

Description

DescriptiveInfoRQ

1

\|Root node.

DescriptiveInfoRQ/Hotel

1

\| Hotel requested.

DescriptiveInfoRQ/Hotel/Code

1

String

Code.

| 
| `toc <#toc>`__

--------------

*DescriptiveInfoRS* Example
'''''''''''''''''''''''''''

::

    <DescriptiveInfoRS>
        <Hotel>
            <Code>70</Code>
            <Name>ILLA</Name>
            <GiataFormatCode>70ES</GiataFormatCode>
            <Address>AVDA. ILLA S/N</Address>
            <Town>HUELVA</Town>
            <ZipCode>21449</ZipCode>
            <CountryISOCode>ES</CountryISOCode>
            <AvailDestination code = "2" name = "HUELVA"/>
            <GeographicDestination code = "2" name = "HUELVA" avail = "true"/>
            <Contact>
                <Email>emailhotel@xxx.com</Email>
                <Telephone>91547892</Telephone>
                <Fax></Fax>
            </Contact>
            <BookingContact>
                <Email>bookinghotel@xxx.com</Email>
                <Telephone>91547880</Telephone>
                <Fax>910200200</Fax>
            </BookingContact>
            <CategoryCode>4 Estrellas</CategoryCode>
            <Type>H</Type>
            <ShortDescription>the hotel.....</ShortDescription>
            <LongDescription>the hotel....</LongDescription>
            <HowToGet></HowToGet>
            <RoomDescription>....</RoomDescription>
            <SituationDescription>....</SituationDescription>
            <Images>
                <Picture>
                    <URL>http://www.images.net/infor/work/imagen/hotel_07/mapa.jpg</URL>
                    <Classification>GRAL</Classification>
                </Picture>
                <Picture>
                    <URL>http://www.images.net/infor/work/imagen/hotel_02/M.jpg</URL>
                    <Classification>GRAL</Classification>
                </Picture>
            </Images>
            <LocationType>City</LocationType>
        </Hotel>
    </DescriptiveInfoRS>

| 
| `toc <#toc>`__

--------------

*DescriptiveInfoRS* Description
'''''''''''''''''''''''''''''''

Element

Number

Type

Description

DescriptiveInfoRS/Hotel

0..n

\|Root node. Hotel sheet.

Code

1

String

Code.

Name

1

String

Name.

Address

1

String

Address.

Town

1

String

Town.

ZipCode

1

String

ZipCode.

CountryISOCode

1

String

CountryISOCode.

AvailDestination

0..1

Avail Destination ( will come only if it is attackable on availability,
and the type is CTY).

*@code*

1

String

Destination code.

*@name*

1

String

Destination name.

GeographicDestination

1

Geographic Destination.

*@code*

1

String

Destination code.

*@name*

1

String

Destination name.

*@avail*

1

Boolean

Indicates if it is attackable on availability.

Latitude

1

String

Latitude.

Longitude

1

String

Longitude.

Contact

0..1

Contact.

Contact/Email

1

String

Email.

Contact/Telephone

1

String

Telephone.

Contact/Fax

1

String

Fax.

CategoryCode

1

String

CategoryCode.

BookingContact

0..1

Booking Contact.

BookingContact/Email

1

String

Email.

BookingContact/Telephone

1

String

Telephone.

BookingContact/Fax

1

String

Fax.

Type

0..1

String

Hotel type: H (hotel) A (apartment) AH (aparthotel) C (club) AT
(agritourism) HS (hostel) CA (house) V (Ville) B (Bungalows).

Chaincode

0..1

String

Chain code.

ShortDescription

0..1

String

Short Description.

LongDescription

0..1

String

Long Description.

HowToGet

0..1

String

How to get description.

RoomDescription

0..1

String

Room description.

SituationDescription

0..1

String

Situation description.

RestaurantsDescription

0..1

String

Restaurants description.

PoolsDescription

0..1

String

Pools description.

ActivitiesDescription

0..1

String

Activities description.

ServicesDescription

0..1

String

Services description.

AdditionalDetails

0..1

String

Additional details.

Attributes

0..1

Attributes.

Attributes/Attribute

1..n

Attribute.

Attributes/Attribute/Code

1

String

Code.

Attributes/Attribute/Value

1

String

Value.

Attributes/Attribute/Classification

1

String

Classification ( HOT=hotel, HAB=room, SER=service and GRAL=generic).

Images

0..1

Images.

Images/Picture

1..n

Picture.

Images/Picture/Url

1

String

Url.

Images/Picture/Classification

1

String

Classification ( HOT=hotel, HAB=room, SER=service and GRAL=generic).

Images/Picture/Ordered

0..1

String

Images should be ordered from 1 onward. 1 is top.

Images/Picture/Description

1

String

Description.

LocationType

0..1

String

CategoryCode.

CategoryCode

1

String

CategoryCode.

| 
| `toc <#toc>`__

--------------