# Flight Listing Displayed

### This event is part of the page load sequence, including virtual page loads in the case of single page apps, and must be pushed between the `Page Load Started` and `Page Load Completed` events.

## Javascript Code
```js
window.appEventData = window.appEventData || [];
appEventData.push({
  "event": "Flight Listing Displayed",
    "airTravel": {
        "bookingInteraction": "<bookingInteraction>",
        "bookingLeadTime": "<bookingLeadTime>",
        "companionFareIndicator": "<companionFareIndicator>",
        "departureDate": "<departureDate>",
        "duration": "<duration>",
        "flightList": [
            {
                "flightDepartureDate": "<flightDepartureDate>",
                "flightId": "<flightId>",
                "flightSequence": "<flightSequence>",
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
|flightDepartureDate|string|The date upon which a flight is scheduled to depart \(in YYYY-MM-DD format\). |2021-10-20, 2022-01-31, 2022-03-03|^[0-9]{4}-[0-9]{2}-[0-9]{2}$||||||
|flightId|string|A two-part string composed of the origin and destination airport codes for a flight with "&gt;" between the airport codes. e.g. YYZ&gt;SFO.  All flights from YYZ to SFO have the same ID regardless of how many stops\/segments are involved.|SFO&gt;YYC, YYC&gt;SFO, ORD&gt;YUL, YXC&gt;LGA|^[A-Z]{3}>[A-Z]{3}$||||||
|flightSequence|integer|The sequence of the flight within a trip.  The returning flight of a Round-Trip would be "2".|1, 2, 3, 4, 5||||1|||
|numAdults|string|A count of adult travelers for a trip.|zero, 1, 2, 3, 4|^([0-9])|(zero)$||||||
|numChildren|string|A count of child travelers for a trip.|zero, 1, 2, 3, 4|^([0-9])|(zero)$||||||
|numFlights|integer|Number of flights within the trip. One-way is always 1. Round-trip is aways two. Multi-City is 2 or more.|1, 2, 3, 4, 5||||1|||
|numInfants|string|A count of infant travelers for a trip.|zero, 1, 2, 3, 4|^([0-9])|(zero)$||||||
|numSeatedGuests|integer|Number of required seats for all travelers on a trip.  Typically adults + children.|1, 2, 3, 4, 5||||1|||
|returnDate|string|Date of return for the last segment of a round trip or multi-city routing.|2021-10-22, 2022-02-21, 2022-03-10|^[0-9]{4}-[0-9]{2}-[0-9]{2}$||||||
|tripId|string|A unique representation of the main departure and arrival points for all primary trip legs \(not including connections\). |SFO&gt;YYC:YYC&gt;SFO, SFO&gt;YYC, SFO&gt;YYC:YYC&gt;YXC:YKA&gt;SFO|^([A-Z]{3}>[A-Z]{3}:?)+$||||||
|tripRouting|string|Describes the routing for a trip. e.g. one way, round trip, or multi-city. |one way, round trip, multi city|||||||



