# KongAir Booking API

## Introduction

Welcome to the **KongAir Booking API**. KongAir offers a seamless flight booking experience through its API, allowing users to search for available flights, create bookings, retrieve booking details, and cancel reservations. This API is ideal for travel agencies, booking platforms, and airline service providers.

## Base URL

```
https://api.kongair.com/v1
```

All endpoints should be prefixed with the above base URL.

## Authentication

The API requires an API key for authentication. Include your API key in the `Authorization` header:

```
Authorization: Bearer YOUR_API_KEY
```

## Endpoints

### Retrieve Available Flights

#### **GET /flights**

Fetch a list of available flights based on search criteria.

#### **Request Parameters**

| Parameter    | Type   | Location | Required | Description                          |
|-------------|--------|----------|----------|--------------------------------------|
| origin      | string | Query    | Yes      | IATA code of the departure airport  |
| destination | string | Query    | Yes      | IATA code of the arrival airport    |
| date        | string | Query    | Yes      | Flight departure date (YYYY-MM-DD)  |

#### **Response**

##### **Success (200 OK)**

```json
[
  {
    "id": "FL1234",
    "origin": "JFK",
    "destination": "LAX",
    "departure_time": "2025-06-01T08:30:00Z",
    "arrival_time": "2025-06-01T11:30:00Z",
    "price": 350.75
  }
]
```

---

### Create a New Booking

#### **POST /bookings**

Reserve seats on a selected flight.

#### **Request Body**

```json
{
  "flight_id": "FL1234",
  "passengers": [
    {
      "first_name": "John",
      "last_name": "Doe",
      "date_of_birth": "1985-05-20",
      "passport_number": "123456789"
    }
  ],
  "payment": {
    "method": "credit_card",
    "amount": 350.75
  }
}
```

#### **Response**

##### **Success (201 Created)**

```json
{
  "id": "BK98765",
  "flight": {
    "id": "FL1234",
    "origin": "JFK",
    "destination": "LAX",
    "departure_time": "2025-06-01T08:30:00Z",
    "arrival_time": "2025-06-01T11:30:00Z",
    "price": 350.75
  },
  "passengers": [
    {
      "first_name": "John",
      "last_name": "Doe",
      "date_of_birth": "1985-05-20",
      "passport_number": "123456789"
    }
  ],
  "status": "confirmed"
}
```

---

### Retrieve Booking Details

#### **GET /bookings/{bookingId}**

Fetch details of an existing booking.

#### **Request Parameters**

| Parameter   | Type   | Location | Required | Description                         |
|------------|--------|----------|----------|-------------------------------------|
| bookingId  | string | Path     | Yes      | Unique identifier of the booking   |

#### **Response**

##### **Success (200 OK)**

```json
{
  "id": "BK98765",
  "flight": {
    "id": "FL1234",
    "origin": "JFK",
    "destination": "LAX",
    "departure_time": "2025-06-01T08:30:00Z",
    "arrival_time": "2025-06-01T11:30:00Z",
    "price": 350.75
  },
  "passengers": [
    {
      "first_name": "John",
      "last_name": "Doe",
      "date_of_birth": "1985-05-20",
      "passport_number": "123456789"
    }
  ],
  "status": "confirmed"
}
```

---

### Cancel a Booking

#### **DELETE /bookings/{bookingId}**

Cancel an existing booking.

#### **Request Parameters**

| Parameter   | Type   | Location | Required | Description                         |
|------------|--------|----------|----------|-------------------------------------|
| bookingId  | string | Path     | Yes      | Unique identifier of the booking   |

#### **Response**

##### **Success (204 No Content)**

---

## Data Models

### **Flight Object**

| Field         | Type     | Description                           |
|--------------|---------|-------------------------------------|
| id           | string  | Unique flight identifier            |
| origin      | string  | Departure airport IATA code         |
| destination | string  | Arrival airport IATA code           |
| departure_time | string | Scheduled departure time (ISO 8601) |
| arrival_time   | string | Scheduled arrival time (ISO 8601)   |
| price        | number  | Flight ticket price (USD)           |

### **Booking Object**

| Field       | Type     | Description                         |
|------------|---------|---------------------------------|
| id         | string  | Unique booking identifier         |
| flight     | object  | Flight details                    |
| passengers | array   | List of passengers                |
| status     | string  | Booking status (`confirmed`, `cancelled`) |

### **Passenger Object**

| Field           | Type   | Description                     |
|----------------|--------|---------------------------------|
| first_name     | string | Passenger’s first name          |
| last_name      | string | Passenger’s last name           |
| date_of_birth  | string | Passenger’s date of birth (YYYY-MM-DD) |
| passport_number | string | Passport number                |

### **Payment Object**

| Field   | Type   | Description                     |
|--------|--------|---------------------------------|
| method | string | Payment method (`credit_card`, `paypal`) |
| amount | number | Transaction amount (USD)        |

## Rate Limits

To ensure fair usage, KongAir enforces rate limits on API requests:

- **Standard Tier**: 1000 requests per hour
- **Enterprise Tier**: 10,000 requests per hour

For higher limits, contact our API support team.

## Support

For issues, feedback, or questions, reach out to **KongAir Developer Support**:

- **Email:** api-support@kongair.com
- **Docs:** https://developer.kongair.com
- **Community Forum:** https://community.kongair.com

## Conclusion

The KongAir Booking API provides a comprehensive solution for flight reservations, offering a seamless booking experience. Start integrating today to streamline air travel for your customers!

