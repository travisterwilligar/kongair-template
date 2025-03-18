---
title: Getting started
description: Get started with our new Developer Portal!
---

::page-section
# Getting Started with KongAir APIs

## Introduction

Welcome to the **KongAir API Suite**, your gateway to seamless air travel integration. Whether you’re a travel platform, an airline service provider, or an enterprise seeking efficient air travel solutions, our APIs offer a comprehensive set of tools to help you book flights, manage passengers, find optimal routes, and retrieve real-time flight details.

KongAir is dedicated to delivering a superior digital travel experience through our **developer-friendly APIs**, **robust infrastructure**, and **reliable data**. Our APIs are built to streamline operations and enhance customer experience.

---

## KongAir API Suite

Our API suite consists of four powerful endpoints designed to provide everything you need to integrate with KongAir’s services:

### 1. **Flights API** - Retrieve Real-Time Flight Details
- **Endpoint:** `/flights/{flightNumber}`
- **Functionality:** Get up-to-date details about any KongAir flight, including departure time, arrival time, delays, meal service, and available seats.
- **Use Case:** Airlines, booking platforms, and travel agents can provide customers with real-time flight status and seat availability.

### 2. **Passenger API** - Access Passenger Profiles
- **Endpoint:** `/passengers/{customerId}`
- **Functionality:** Retrieve passenger details, including loyalty status, recent flights, and purchase history.
- **Use Case:** Travel agencies and customer service representatives can personalize services for frequent flyers and enhance the travel experience.

### 3. **Routes API** - Discover the Shortest Flight Routes
- **Endpoint:** `/routes?origin={origin}&destination={destination}`
- **Functionality:** Retrieve optimized flight routes between two destinations.
- **Use Case:** Travel planners and logistics companies can calculate the best flight paths for customers or cargo.

### 4. **Bookings API** - Manage Flight Reservations
- **Endpoints:**
  - `GET /flights` (search flights)
  - `POST /bookings` (create a booking)
  - `GET /bookings/{bookingId}` (retrieve booking details)
  - `DELETE /bookings/{bookingId}` (cancel a booking)
- **Functionality:** Enables flight search, booking creation, and reservation management.
- **Use Case:** Travel agencies and online booking platforms can integrate KongAir’s reservation system into their applications.

---

## Why Choose KongAir APIs?

### 🚀 **Fast & Reliable**
Our APIs are built on **high-performance infrastructure** to ensure minimal latency and maximum uptime.

### 🔒 **Secure & Compliant**
KongAir follows **industry best practices** for security and data privacy, ensuring all transactions and passenger data are protected.

### 📡 **Real-Time Data**
Get accurate flight statuses, routes, and booking details with **up-to-the-minute updates**.

### 🔧 **Developer-Friendly**
Our APIs are designed with **RESTful principles**, making them easy to integrate with any modern application.

---

## Authentication & Access

All KongAir APIs require an **API Key** for authentication.

### How to Get Your API Key:
1. Sign up at [KongAir Developer Portal](https://4fa1d89c1435.edge.us.portal.konghq.com/register).
2. Navigate to the **API Keys** section.
3. Generate your API Key and use it in your requests:
```
Authorization: Bearer YOUR_API_KEY
```

---

## Rate Limits

To ensure fair usage, KongAir enforces rate limits:
- **Standard Tier**: 1,000 requests per hour
- **Enterprise Tier**: 10,000 requests per hour

For higher limits, contact our sales team at **sales@kongair.com**.

---

## Developer Support & Community

We’re committed to helping you succeed with KongAir’s APIs.

### 📞 **Support Options**
- **Email Support:** api-support@kongair.com
- **Live Chat:** Available via the 
- **Dedicated Account Manager** (Enterprise Customers Only)

### 🌍 **Join Our Developer Community**
- **Community Forum:** Discuss best practices and integration tips with other developers.
- **API Changelog:** Stay updated on new features and improvements.
- **Webinars & Tutorials:** Learn how to maximize KongAir APIs with step-by-step guidance.

---

## Start Building Today!

KongAir’s APIs provide a seamless way to integrate with our airline services and enhance your travel-related applications. Get started today by signing up for an API key, exploring our documentation, and joining our developer community.


✈️ **Fly smarter with KongAir APIs!**
::
