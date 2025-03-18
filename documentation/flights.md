# KongAir Flights API

## Introduction

Welcome to the **KongAir Flights API**. KongAir is a world-class airline committed to providing superior travel experiences across the globe. Whether you're booking a transatlantic journey or a quick domestic hop, KongAir ensures a seamless and luxurious flight experience with cutting-edge technology and exceptional service.

The **KongAir Flights API** allows developers to retrieve detailed flight information, including schedules, aircraft details, available seating, and real-time flight statuses. This API is designed for travel agencies, mobile applications, and airport information systems that need real-time flight data.

## Base URL

```
https://api.kongair.com/v1
```

All endpoints should be prefixed with the above base URL.

## Authentication

The API uses API keys for authentication. To access the API, include your API key in the `Authorization` header:

```
Authorization: Bearer YOUR_API_KEY
```

## Endpoints

### Retrieve Flight Information

#### **GET /flights/{flightNumber}**

Fetch detailed information about a specific flight using its unique flight number.

#### **Request Parameters**

| Parameter      | Type   | Location | Required | Description                                      |
|-------------- |------  |----------|----------|-------------------------------------------------|
| flightNumber  | string | Path     | Yes      | Unique flight number (e.g., `KA1234`)          |

#### **Response**

##### **Success (200 OK)**

```json
{
  "flight_number": "KA1234",
  "origin": "JFK",
  "destination": "LAX",
  "departure_time": "2025-06-01T08:30:00Z",
  "arrival_time": "2025-06-01T11:30:00Z",
  "duration": "06:15:00",
  "airplane": {
    "model": "Boeing 787",
    "registration_number": "N123KA",
    "total_seats": 250,
    "airline": "KongAir"
  },
  "available_seats": {
    "economy": 42,
    "business": 10,
    "first_class": 4
  },
  "meals": {
    "economy": "Snack and beverage",
    "business": "Three-course meal",
    "first_class": "Gourmet dining experience with wine pairing"
  },
  "status": "scheduled",
  "active_delays": [
    "Weather-related delay of 30 minutes."
  ]
}
```

##### **Error Responses**

| Status Code | Description                          |
|------------|----------------------------------|
| 400        | Invalid flight number format    |
| 404        | Flight not found                |
| 500        | Internal server error           |

## Data Models

### **Flight Object**

| Field            | Type     | Description                                     |
|-----------------|---------|-------------------------------------------------|
| flight_number   | string  | Unique flight identifier                        |
| origin         | string  | Airport IATA code for departure location       |
| destination    | string  | Airport IATA code for arrival location         |
| departure_time | string  | Scheduled departure time (ISO 8601 format)      |
| arrival_time   | string  | Scheduled arrival time (ISO 8601 format)        |
| duration       | string  | Total flight duration (HH:MM:SS)                |
| airplane       | object  | Details about the aircraft                      |
| available_seats| object  | Seat availability in different classes          |
| meals         | object  | In-flight meal options based on class           |
| status        | string  | Current flight status (`scheduled`, `delayed`, `cancelled`, `departed`, `landed`) |
| active_delays | array   | List of active delays (if applicable)           |

### **Airplane Object**

| Field              | Type   | Description                              |
|-------------------|-------|----------------------------------|
| model            | string | Aircraft model (e.g., Boeing 787)   |
| registration_number | string | Unique aircraft registration number |
| total_seats      | integer | Total seating capacity of the aircraft |
| airline         | string | Airline operating the aircraft ("KongAir") |

## Usage Example

Here’s how a client application might fetch flight details:

```bash
curl -H "Authorization: Bearer YOUR_API_KEY" \
     -X GET "https://api.kongair.com/v1/flights/KA1234"
```

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

The KongAir Flights API provides comprehensive and real-time flight information to help partners and developers build next-generation travel applications. Start integrating today and elevate your travel experiences with KongAir!

