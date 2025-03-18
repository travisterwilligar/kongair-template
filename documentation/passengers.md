# KongAir Passenger API

## Introduction

Welcome to the **KongAir Passenger API**. KongAir is committed to delivering seamless, world-class travel experiences by leveraging modern technology. Our Passenger API enables authorized applications to access passenger details, loyalty program status, recent flight history, and transaction records. This API is designed for use by travel partners, airport systems, and customer service platforms.

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

### Retrieve Passenger Information

#### **GET /passengers/{customerId}**

Fetch detailed information about a specific passenger using their unique customer ID.

#### **Request Parameters**

| Parameter     | Type   | Location | Required | Description                  |
|--------------|--------|----------|----------|------------------------------|
| customerId   | string | Path     | Yes      | Unique customer ID (e.g., `CUST12345`) |

#### **Response**

##### **Success (200 OK)**

```json
{
  "customer_id": "CUST12345",
  "first_name": "John",
  "middle_name": "Michael",
  "last_name": "Doe",
  "email": "john.doe@example.com",
  "phone_number": "+1-555-123-4567",
  "address": {
    "street": "123 Main St",
    "city": "Los Angeles",
    "state": "CA",
    "postal_code": "90001",
    "country": "USA"
  },
  "employer": "Acme Corp",
  "loyalty_status": {
    "tier": "Gold",
    "points_balance": 25000,
    "status_valid_until": "2026-12-31"
  },
  "recent_flights": [
    {
      "flight_number": "KA5678",
      "origin": "JFK",
      "destination": "LAX",
      "departure_date": "2024-05-15",
      "class": "Business",
      "seat_number": "12A"
    }
  ],
  "recent_purchases": [
    {
      "purchase_id": "PUR78901",
      "description": "Extra baggage allowance",
      "amount": 50.00,
      "purchase_date": "2025-02-20T14:30:00Z"
    }
  ]
}
```

##### **Error Responses**

| Status Code | Description                          |
|------------|----------------------------------|
| 400        | Invalid customer ID format      |
| 404        | Passenger not found             |
| 500        | Internal server error           |

## Data Models

### **Passenger Object**

| Field           | Type   | Description                             |
|----------------|--------|-----------------------------------------|
| customer_id    | string | Unique customer identifier             |
| first_name     | string | Passenger's first name                 |
| middle_name    | string | Passenger's middle name (if available) |
| last_name      | string | Passenger's last name                  |
| email          | string | Passenger's email address              |
| phone_number   | string | Contact phone number                   |
| address        | object | Full address details                   |
| employer       | string | Employer name (if available)           |
| loyalty_status | object | Details on passenger's loyalty program |
| recent_flights | array  | List of past flights                   |
| recent_purchases | array | List of recent purchases made with KongAir |

### **Loyalty Status Object**

| Field              | Type   | Description                              |
|-------------------|--------|----------------------------------|
| tier             | string | Loyalty program tier (`Bronze`, `Silver`, `Gold`, `Platinum`) |
| points_balance   | integer | Current loyalty points balance |
| status_valid_until | string | Expiry date of the current status |

### **Flight History Object**

| Field           | Type   | Description                            |
|----------------|--------|----------------------------------------|
| flight_number  | string | Flight identifier                      |
| origin         | string | Departure airport IATA code           |
| destination    | string | Arrival airport IATA code             |
| departure_date | string | Date of flight (YYYY-MM-DD)           |
| class         | string | Ticket class (`Economy`, `Business`, `First`) |
| seat_number   | string | Assigned seat number                   |

### **Purchase Object**

| Field          | Type   | Description                            |
|---------------|--------|----------------------------------------|
| purchase_id   | string | Unique purchase identifier             |
| description   | string | Description of the purchase            |
| amount       | number | Transaction amount (USD)               |
| purchase_date | string | Date and time of purchase (ISO 8601)   |

## Usage Example

Here’s how a client application might retrieve passenger details:

```bash
curl -H "Authorization: Bearer YOUR_API_KEY" \
     -X GET "https://api.kongair.com/v1/passengers/CUST12345"
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

The KongAir Passenger API provides comprehensive and secure access to passenger profiles, loyalty status, and recent transactions. Whether you're enhancing customer service or integrating travel solutions, KongAir empowers your applications with rich passenger data. Start integrating today and elevate your travel experiences with KongAir!

