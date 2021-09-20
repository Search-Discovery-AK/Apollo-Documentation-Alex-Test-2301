# Flight Segment Seats Selected

### 

## Javascript Code
```js
window.appEventData = window.appEventData || [];
appEventData.push({
  "event": "Flight Segment Seats Selected",
    "airTravel": {
        "bookingInteraction": "<bookingInteraction>",
        "bookingLeadTime": "<bookingLeadTime>",
        "companionFareIndicator": "<companionFareIndicator>",
        "departureDate": "<departureDate>",
        "duration": "<duration>",
        "flightList": [
            {
                "flightArrivalDate": "<flightArrivalDate>",
                "flightBaseFare": "<flightBaseFare>",
                "flightDepartureDate": "<flightDepartureDate>",
                "flightDuration": "<flightDuration>",
                "flightFareBundle": "<flightFareBundle>",
                "flightFareClass": "<flightFareClass>",
                "flightId": "<flightId>",
                "flightNumSegments": "<flightNumSegments>",
                "flightSegmentAutoSeatSelectionStatus": "<flightSegmentAutoSeatSelectionStatus>",
                "flightSegmentDesignator": "<flightSegmentDesignator>",
                "flightSegmentDuration": "<flightSegmentDuration>",
                "flightSegmentEquipment": "<flightSegmentEquipment>",
                "flightSegmentGuestCabin": "<flightSegmentGuestCabin>",
                "flightSegmentGuestNumber": "<flightSegmentGuestNumber>",
                "flightSegmentGuestSSRCodes": "<flightSegmentGuestSSRCodes>",
                "flightSegmentGuestSeat": "<flightSegmentGuestSeat>",
                "flightSegmentGuestSeatCost": "<flightSegmentGuestSeatCost>",
                "flightSegmentGuestType": "<flightSegmentGuestType>",
                "flightSegmentId": "<flightSegmentId>",
                "flightSegmentOperator": "<flightSegmentOperator>",
                "flightSegmentSeatSelectionMethod": "<flightSegmentSeatSelectionMethod>",
                "flightSegmentSequence": "<flightSegmentSequence>",
                "flightSequence": "<flightSequence>",
                "flightTotalFare": "<flightTotalFare>",
                "tripId": "<tripId>"
            }
        ],
        "numAdults": "<numAdults>",
        "numChildren": "<numChildren>",
        "numFlights": "<numFlights>",
        "numInfants": "<numInfants>",
        "numSeatedGuests": "<numSeatedGuests>",
        "returnDate": "<returnDate>",
        "tripRouting": "<tripRouting>"
    },
    "voucherDiscount": {
        "discountCode": "<discountCode>",
        "discountCodeStatus": "<discountCodeStatus>"
    }
});
```

## Variable Definitions

|Field|Type|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|bookingInteraction|string|Captures the various interactions within the Trip Booking flow. |Flight Search Performed, Flight Listing Displayed, Flight Summary Displayed, Guest Info Form Displayed, Flight Segment Seat Map Displayed|||||||
|bookingLeadTime|string|Number of days ahead of departure for the first segment of a trip.|zero, 1, 20, 22, 33|^([0-9])|(zero)$||||||
|companionFareIndicator|string|An indication of whether a companion fare is available \/ being requested \/ used for the trip.|available, unavailable, in use|||||||
|departureDate|string|Date of departure for the first segment of a trip.|2021-10-20, 2022-01-31, 2022-03-03|^[0-9]{4}-[0-9]{2}-[0-9]{2}$||||||
|discountCode|string|Discount code entered or applied|5OFFSHOES, AKRONCANDLES2019|||||||
|discountCodeStatus|string|Indicates whether a discount code is valid, expired, or invalid.|valid, invalid, expired|||||||
|duration|integer|Number of days from the first segment departure to the final segment departure. For One-Way trips, the duration is always 1.|1, 3, 5, 14, 20||||1|||
|flightArrivalDate|string|The date upon which a flight is scheduled to arrive \(in YYYY-MM-DD format\). |2021-10-20, 2022-01-31, 2022-03-03|^([0-9]{4}-[0-9]{2}-[0-9]{2})?$||||||
|flightBaseFare|string|The base fare of the flight only in the currency displayed to the user. ||^[0-9]*(\.[0-9]{1,2})?$||||||
|flightDepartureDate|string|The date upon which a flight is scheduled to depart \(in YYYY-MM-DD format\). |2021-10-20, 2022-01-31, 2022-03-03|^[0-9]{4}-[0-9]{2}-[0-9]{2}$||||||
|flightDuration|string|The total duration of the flight \(in minutes\) from departure to arrival at final destination including time in flight and layovers. |46, 90, 120, 204|||||||
|flightFareBundle|string|Flight Fare Bundle describes the fare bundle chosen by the user. e.g. Basic, Econo, EconoRewards|Basic, Econo, EconoRewards, EconoFlex, Premium|||||||
|flightFareClass|string|Describes the fare class for a flight \(e.g. E,X, or B\)|E, B, X|||||||
|flightId|string|A two-part string composed of the origin and destination airport codes for a flight with "&gt;" between the airport codes. e.g. YYZ&gt;SFO.  All flights from YYZ to SFO have the same ID regardless of how many stops\/segments are involved.|SFO&gt;YYC, YYC&gt;SFO, ORD&gt;YUL, YXC&gt;LGA|^[A-Z]{3}>[A-Z]{3}$||||||
|flightNumSegments|integer|The number of segments between the flight origin and final destination.|1, 2, 3, 4||||1|||
|flightSegmentAutoSeatSelectionStatus|string|Indicates if automatic seat selection is avaiable or unavailable for a flight segment.|Available, Unavailable|||||||
|flightSegmentDesignator|string|A combination of a two character airline code and a numeric flight number. \(e.g. WJ1521\)|WJ1515, WJ501, DL2745, AA55|^[A-Z]{2}[1-9][0-9]{0,3}$||||||
|flightSegmentDuration|integer|The total duration of the flight segment \(in minutes\). |35, 55, 90, 122|||||||
|flightSegmentEquipment|string|The equipment that flies a flight segment. \(e.g. Boeing 737 MAX 8\)|Boeing 737-600, Boeing 737 MAX 8, De Havilland Dash8 Q400, Saab 340B, Embraer 175|||||||
|flightSegmentGuestCabin|string|Describes the cabin section where the seat exists. \(e.g. economy, economy-plus, premier, business, 1st class\)|economy, economy-plus, business, premier, first class|||||||
|flightSegmentGuestNumber|integer|Indicates to which a seat is assigned in multiple guest bookings. |1, 2, 3, 4||||1|||
|flightSegmentGuestSSRCodes|string|Captures all Special Services Request codes for the guest. |deaf, blnd\~deaf\~wchr, blind, no SSR codes|||||||
|flightSegmentGuestSeat|string|Describes the selected seat. May be simple \(e.g. '16D'\) or overloaded \(e.g. '3E\~3\~E\~Aisle\~NoExitRow'\)|3B, 16E, 3E\~3\~E\~Aisle\~NoExitRow, 11B\~11\~B\~Middle\~ExitRow|||||||
|flightSegmentGuestSeatCost|string|The cost of the seat above that included in the fare.  \(e.g. 'zero', '19', '27'\)|zero, 19, 27, 45|^([1-9][0-9]{0,2})|(zero)$||||||
|flightSegmentGuestType|string|Indicates if the guest is an Adult or Child \(or other as desired e.g. Military, Veteran, etc\)|Adult, Child, Active Military, Veteran|||||||
|flightSegmentId|string|A two-part string composed of the origin and destination airport codes for a segment with "&gt;" between the airport codes. e.g. YYZ&gt;SFO.  |SFO&gt;YYC, YYC&gt;SFO, ORD&gt;YUL, YXC&gt;LGA|^[A-Z]{3}>[A-Z]{3}$||||||
|flightSegmentOperator|string|The airline that operates a flight segment. \(e.g. WestJet, Delta\)|WestJet, Delta, American Airlines, TWA|||||||
|flightSegmentSeatSelectionMethod|string|Indicates the method used for seat selection. This might be 'Unselected' , 'Manual',  'Auto Selection', or 'Auto Selection Failure'|Manual, Auto Selected, AutoSelect Failure|||||||
|flightSegmentSequence|integer|The sequence of a segment withing a flight.  The first segment of a flight is sequence 1.|1, 2, 3, 4||||1|||
|flightSequence|integer|The sequence of the flight within a trip.  The returning flight of a Round-Trip would be "2".|1, 2, 3, 4, 5||||1|||
|flightTotalFare|string|The total fare for the flight including Base Fare and Taxes in the currency displayed to the user. ||^[0-9]*(\.[0-9]{1,2})?$||||||
|numAdults|string|A count of adult travelers for a trip.|zero, 1, 2, 3, 4|^([0-9])|(zero)$||||||
|numChildren|string|A count of child travelers for a trip.|zero, 1, 2, 3, 4|^([0-9])|(zero)$||||||
|numFlights|integer|Number of flights within the trip. One-way is always 1. Round-trip is aways two. Multi-City is 2 or more.|1, 2, 3, 4, 5||||1|||
|numInfants|string|A count of infant travelers for a trip.|zero, 1, 2, 3, 4|^([0-9])|(zero)$||||||
|numSeatedGuests|integer|Number of required seats for all travelers on a trip.  Typically adults + children.|1, 2, 3, 4, 5||||1|||
|returnDate|string|Date of return for the last segment of a round trip or multi-city routing.|2021-10-22, 2022-02-21, 2022-03-10|^[0-9]{4}-[0-9]{2}-[0-9]{2}$||||||
|tripId|string|A unique representation of the main departure and arrival points for all primary trip legs \(not including connections\). |SFO&gt;YYC:YYC&gt;SFO, SFO&gt;YYC, SFO&gt;YYC:YYC&gt;YXC:YKA&gt;SFO|^([A-Z]{3}>[A-Z]{3}:?)+$||||||
|tripRouting|string|Describes the routing for a trip. e.g. one way, round trip, or multi-city. |one way, round trip, multi city|||||||



