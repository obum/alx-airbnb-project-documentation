# 🏠 ALX Airbnb Clone – Use Case Documentation

This document outlines the core **user stories**, **actors**, **use cases**, and **functional requirements** that drive the backend architecture of the Airbnb Clone project.

## 👥 Actors

| Actor             | Description                                                               |
|------------------|---------------------------------------------------------------------------|
| **Guest**         | Registers, searches listings, books properties, makes payments, and reviews. |
| **Host**          | Lists properties, manages listings/bookings, and responds to reviews.       |
| **Admin**         | Monitors users, listings, bookings, and payments.                          |
| **Payment Gateway** | External service for processing secure transactions and payouts.           |

---

## ✅ Core Use Cases

### 🧍‍♂️ User Management
- Register as Guest/Host  
- Login / OAuth Login (Google, Facebook)  
- Manage Profile  

### 🏘️ Property Listing
- Add/Edit/Delete Listing (Host)  
- View Listings  
- Approve Listings (Admin)  

### 🔍 Search & Filtering
- Search by Location, Price, Amenities  
- View Property Details  

### 📅 Booking Management
- Book Property  
- Cancel Booking  
- View Booking Status  

### 💳 Payment Integration
- Make Payment (Guest)  
- Receive Payout (Host)  
- Process Payment (Payment Gateway)  

### 🌟 Reviews & Ratings
- Leave a Review (Guest)  
- Respond to Review (Host)  

### 🔔 Notifications System
- Receive Notifications (Guest, Host)

### 🛠️ Admin Management
- Manage Users  
- Manage Listings  
- Monitor Bookings & Payments  

---

## 📚 User Stories

### 1. User Registration and Profile Management
**As a new user**, I want to register as a guest or host using my email or Google login so that I can access platform features and update my profile.  

**Acceptance Criteria**:
- Register via email or OAuth (Google, Facebook)
- Assign role as Guest or Host
- Update profile photo, contact info, and preferences

---

### 2. Host Property Listing Management
**As a host**, I want to add, update, or delete listings so that I can manage my available rentals.  

**Acceptance Criteria**:
- Provide title, description, price, images, amenities, and availability
- Host can edit or remove listings
- Admin gets notified for listing approval

---

### 3. Guest Property Search and Booking
**As a guest**, I want to search for properties by location, price, and amenities so I can make a reservation that suits my needs.  

**Acceptance Criteria**:
- Filter search results
- View property details
- Book selected property with date validation

---

### 4. Secure Payments and Payouts
**As a guest**, I want to make secure payments for bookings, and **as a host**, I want to receive payouts after successful stays.  

**Acceptance Criteria**:
- Secure payment gateway integration (Stripe/PayPal)
- Automatic payout to host after booking completion
- Support for multiple currencies

---

### 5. Reviews and Notifications
**As a guest**, I want to leave a review after my stay, and **as a host**, I want to respond to it and receive notifications about bookings.  

**Acceptance Criteria**:
- Guests can leave reviews only after a booking
- Hosts can respond once per guest review
- Notification system alerts users for booking, payment, and cancellation updates

---

## 🧩 Development Tasks (GitHub Issues)

### 🔐 User Management
- [ ] Create registration endpoint (Guest/Host)
- [ ] Add OAuth login support
- [ ] Implement JWT-based login
- [ ] Design user profile schema
- [ ] Enable profile update functionality

### 🏠 Property Listings
- [ ] Add listing creation endpoint with image upload
- [ ] Edit/Delete listing routes (only accessible by Host)
- [ ] Admin approval logic for new listings

### 🔍 Search and Filtering
- [ ] Search API with filters: location, price, amenities
- [ ] Pagination and full-text search support
- [ ] View detailed property information

### 🧾 Booking System
- [ ] Booking creation with availability checks
- [ ] Prevent overlapping bookings
- [ ] View booking status and history
- [ ] Implement booking cancellation logic

### 💰 Payments & Payouts
- [ ] Stripe/PayPal integration
- [ ] Payment route triggered on confirmed bookings
- [ ] Payout logic to credit Host after stay
- [ ] Log all transaction metadata

### 🗨️ Reviews and Notifications
- [ ] Review submission feature (Guests only)
- [ ] One-time Host response to each review
- [ ] In-app and email notifications using SendGrid/Firebase

### ⚙️ Admin Dashboard
- [ ] Manage all users, listings, and bookings
- [ ] Monitor payments and resolve disputes
- [ ] Approve or reject new property listings

---