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

GET /flights/search

Query Parameters

### Query Parameters

| Parameter | Type   | Required | Description                        |
|-----------|--------|----------|------------------------------------|
| from      | string | Yes      | Departure airport code (e.g., BOM) |
| to        | string | Yes      | Arrival airport code (e.g., DEL)   |
| date      | string | Yes      | Travel date (YYYY-MM-DD)           |
| adults    | int    | No       | Number of passengers               |



