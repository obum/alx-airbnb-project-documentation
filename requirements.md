# 📄 Backend Feature Requirement Specifications

---

## 🔐 1. User Authentication

### 🧩 Functional Requirements
- Users must be able to register as a **Guest** or **Host**
- Support **OAuth login** with providers like Google or Facebook
- Return secure **JWT tokens** for session management
- Allow users to update profile info and preferences

### 🔗 API Endpoints

| Method | Endpoint              | Description                   |
|--------|-----------------------|-------------------------------|
| POST   | `/api/register`       | Register a new user           |
| POST   | `/api/login`          | Authenticate user login       |
| POST   | `/api/oauth/google`   | Login via Google OAuth        |
| GET    | `/api/profile`        | Get authenticated user info   |
| PUT    | `/api/profile`        | Update profile data           |

### 📥 Sample Input – `/api/register`
```json
{
  "full_name": "Jane Doe",
  "email": "jane@example.com",
  "password": "password123",
  "role": "host"
}
```
###  Sample Output
```json
{
  "message": "Registration successful",
  "token": "eyJhbGciOiJIUzI1..."
}
```
### ✅ Validation Rules
Email must be unique and properly formatted

Password minimum length: 8 characters; must include at least 1 letter and 1 digit

Role must be either guest or host

### ⚙️ Performance Criteria
Response time: ≤ 500ms

Rate limiting: Max 20 registration requests/hour per IP

JWT token expiry: 24 hours (refresh required on login)

---

## 🏘️ 2. Property Management

### 🧩 Functional Requirements
- Only registered **Hosts** can list properties
- Listings must include location, price, amenities, images, etc.
- Listings must be **approved by an Admin** before going live
- Hosts can **edit** or **remove** their listings

---

### 🔗 API Endpoints

| Method | Endpoint                      | Description                  |
|--------|-------------------------------|------------------------------|
| POST   | `/api/listings`               | Create new listing           |
| GET    | `/api/listings`               | Fetch all active listings    |
| GET    | `/api/listings/:id`           | Get single listing details   |
| PUT    | `/api/listings/:id`           | Update listing (host only)   |
| DELETE | `/api/listings/:id`           | Delete listing               |
| POST   | `/api/listings/:id/approve`   | Admin approves listing       |

---

### 📥 Sample Input – `POST /api/listings`
```json
{
  "title": "Cozy Studio in Lekki",
  "description": "10 mins from the beach!",
  "location": "Lekki Phase 1",
  "price_per_night": 15000,
  "amenities": ["WiFi", "AC"],
  "images": ["img1.jpg", "img2.jpg"]
}
```
### Sample Output
```json
{
  "message": "Listing created and pending admin approval.",
  "listing_id": "abc123"
}
```
---

### ✅ Validation Rules
price_per_night must be a positive number

location must include a city or clearly identifiable area

At least one image is required

Only Admin users can approve listings

### ⚙️ Performance Criteria
Search queries: ≤ 700ms with filters

Pagination limit: 20 listings per page

Frequently accessed listings should be cached for speed

---
## 📅 3. Booking System

### 🧩 Functional Requirements
- Guests can **book available properties** for specific dates
- The system must **prevent overlapping bookings** via date validation
- Bookings should support lifecycle statuses:
  - `pending`
  - `confirmed`
  - `canceled`
  - `completed`
- Allow users to **cancel bookings** according to policy
- Each booking must be **linked to a property and a guest**

---

### 🔗 API Endpoints

| Method | Endpoint                     | Description                           |
|--------|------------------------------|---------------------------------------|
| POST   | `/api/bookings`              | Create a new booking                  |
| GET    | `/api/bookings`              | View authenticated user's bookings    |
| GET    | `/api/bookings/:id`          | Retrieve details of a specific booking|
| PUT    | `/api/bookings/:id/cancel`   | Cancel an existing booking            |

---

### 📥 Sample Input – `POST /api/bookings`
```json
{
  "property_id": "prop789",
  "start_date": "2025-07-01",
  "end_date": "2025-07-04",
  "guests": 2
}
```

### Sample Output
```json
{
  "message": "Booking created. Pending payment.",
  "booking_id": "bk123",
  "status": "pending"
}
```
---

### ✅ Validation Rules
start_date must be earlier than end_date

Booking dates must not overlap with existing confirmed bookings

Property must be approved and available

User must be authenticated as a Guest

guests must be a positive integer within the property's capacity (if applicable)

### ⚙️ Performance Criteria
Availability checks should complete in ≤ 400ms

System must handle concurrent booking requests efficiently

Updates to booking status should trigger:

In-app and email notifications

Payment session initiation (if applicable)
