# Overview

The Flight Booking API allows clients to search flights, check availability, and create bookings.
All endpoints follow REST principles and return JSON responses.

# Base URL

https://api.example.com/v1

# Authentication
Use **Bearer Token** for all requests.

**Header:**

Authorization: Bearer <access_token>
Content-Type: application/json

# Endpoints

## Search Flights

**GET**/flights/search

Query Parameters

### Query Parameters

| Parameter | Type   | Required | Description                        |
|-----------|--------|----------|------------------------------------|
| from      | string | Yes      | Departure airport code (e.g., BOM) |
| to        | string | Yes      | Arrival airport code (e.g., DEL)   |
| date      | string | Yes      | Travel date (YYYY-MM-DD)           |
| adults    | int    | No       | Number of passengers               |

Sample Request

GET /flights/search?from=BOM&to=DEL&date=2025-02-10&adults=1

**Sample Response**

```json
{
  "flights": [
    {
      "flightId": "AI202",
      "airline": "Air India",
      "price": 5200,
      "departure": "2025-02-10T09:00:00",
      "arrival": "2025-02-10T11:00:00"
    }
  ]
}
```
## Book a Flight

**POST** /booking/create
```json
{
  "flightId": "AI202",
  "passenger": {
    "name": "Rahul Sharma",
    "age": 29,
    "email": "rahul@example.com"
  }
}
```
**Sample Response**
```json
{
  "bookingId": "BK987654",
  "status": "confirmed",
  "totalAmount": 5200
}
```
## Get Booking Details
**GET** /booking/{bookingId}

**Sample Response**
```json
{
  "bookingId": "BK987654",
  "flightId": "AI202",
  "passengerName": "Rahul Sharma",
  "status": "confirmed"
}
```
# **Error Codes**
| Code | Message      | Meaning               |
|------|--------------|-----------------------|
| 400  | Bad Request  | Invalid input         |
| 401  | Unauthorized | Missing/invalid token |
| 404  | Not Found    | Resource not found    |
| 500  | Server Error | Something went wrong  |

??? note "Click to expand"
    Hidden content here.









