# KongAir Route API

## Introduction

Welcome to the **KongAir Route API**. KongAir is dedicated to providing efficient and reliable air travel across the globe. This API allows applications to retrieve the shortest flight route between two airports, making it an essential tool for travel planning, flight search engines, and logistics optimization.

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

### Retrieve the Shortest Flight Route

#### **GET /routes**

Retrieve the shortest available flight path from a specified origin to a destination.

#### **Request Parameters**

| Parameter    | Type   | Location | Required | Description                          |
|-------------|--------|----------|----------|--------------------------------------|
| origin      | string | Query    | Yes      | IATA code of the departure airport (e.g., `JFK`) |
| destination | string | Query    | Yes      | IATA code of the arrival airport (e.g., `LAX`) |

#### **Response**

##### **Success (200 OK)**

```json
{
  "origin": "JFK",
  "destination": "LAX",
  "total_distance": 3972.0,
  "total_duration": "06:15:00",
  "flights": [
    {
      "flight_number": "KA1234",
      "airline": "KongAir",
      "departure_airport": "JFK",
      "arrival_airport": "LAX",
      "departure_time": "2025-06-01T08:30:00Z",
      "arrival_time": "2025-06-01T11:30:00Z",
      "duration": "06:15:00"
    }
  ]
}
```

##### **Error Responses**

| Status Code | Description                          |
|------------|----------------------------------|
| 400        | Missing or invalid parameters    |
| 404        | No available route found        |
| 500        | Internal server error           |

## Data Models

### **Route Object**

| Field           | Type     | Description                                     |
|----------------|---------|-------------------------------------------------|
| origin        | string  | Departure airport IATA code                     |
| destination   | string  | Arrival airport IATA code                       |
| total_distance | number  | Total distance of the route in kilometers       |
| total_duration | string  | Estimated total duration of the route (HH:MM:SS) |
| flights       | array   | List of flights making up the shortest route    |

### **Flight Segment Object**

| Field             | Type     | Description                                    |
|------------------|---------|----------------------------------------------|
| flight_number    | string  | Unique identifier for the flight              |
| airline         | string  | Operating airline (always `KongAir`)         |
| departure_airport | string  | Departure airport IATA code                   |
| arrival_airport  | string  | Arrival airport IATA code                     |
| departure_time   | string  | Scheduled departure time (ISO 8601 format)    |
| arrival_time     | string  | Scheduled arrival time (ISO 8601 format)      |
| duration        | string  | Flight duration (HH:MM:SS)                     |

## Usage Example

Here’s how a client application might query for the shortest route:

```bash
curl -H "Authorization: Bearer YOUR_API_KEY" \
     -X GET "https://api.kongair.com/v1/routes?origin=JFK&destination=LAX"
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

The KongAir Route API provides accurate and efficient flight routing data, helping applications deliver seamless travel experiences. Whether you're integrating a booking platform or optimizing travel logistics, this API ensures your customers find the best flight routes available. Start integrating today with KongAir!