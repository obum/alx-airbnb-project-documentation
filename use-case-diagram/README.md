# Use Case Diagram of the Features and Functionalities

![Airbnb Usecase diagram](<Use case diagram_Airbnb Clone project.png>)

## 👥 Actors

| Actor             | Description                                                               |
|------------------|---------------------------------------------------------------------------|
| **Guest**         | Registers, searches listings, books properties, makes payments, and reviews. |
| **Host**          | Lists properties, manages listings/bookings, and responds to reviews.       |
| **Admin**         | Monitors users, listings, bookings, and payments.                          |
| **Payment Gateway** | External service for processing secure transactions and payouts.           |

---

## 📌 Main Use Cases
Grouped by major functionalities:

### 🧍‍♂️ User Management
Register as Guest/Host

Login / OAuth Login

Manage Profile

### 🏘️ Property Listing
Add/Edit/Delete Listing (Host)

View Listings

Approve Listings (Admin)

### 🔍 Search & Filtering
Search by location, price, amenities

View property details

### 📅 Booking Management
Book Property

Cancel Booking

View Booking Status

### 💳 Payment Integration
Make Payment (Guest)

Receive Payout (Host)

Process Payment (Gateway)

### 🌟 Reviews & Ratings
Leave a Review (Guest)

Respond to Review (Host)

### 🔔 Notifications System
Receive Notifications (Guest, Host)

### 🛠️ Admin Management
Manage Users

Manage Listings

Monitor Bookings & Payments

### Guest Interactions
These are the actions a Guest can perform:

Register / Login – Sign up or log into the platform.

Search Property – Look up properties using filters (location, price, amenities).

View Property Details – Click into a listing for full info.

Book Property – Choose dates and reserve a listing.

Make Payment – Complete booking with a payment method.

Leave Review – Share feedback after their stay.

Cancel Booking – Withdraw from a booking if needed.

Receive Notifications – Get alerts for confirmations, changes, or updates.

🟢 These interactions are shown by arrows pointing from Guest to each use case.

## ost Interactions
The Host has the following responsibilities:

Register / Login – Sign into the system.

Add/Edit/Delete Listing – Create or modify property details.

Manage Bookings – Approve or prepare for guest stays.

Respond to Reviews – Provide feedback or replies to guest comments.

Receive Notifications – Stay updated on bookings and reviews.

🔵 These actions are linked from Host to their respective use cases.

## Admin Activities
Admins are central to governance. They can:

Approve Listings – Vet and enable host properties.

Monitor Users & Listings – Review any suspicious or policy-breaking content.

Manage Payments & Bookings – Oversee platform activity and disputes.

🟡 Admin’s actions are generally linked to backend management.

## Payment Gateway Interaction
This actor enables:

Process Payments – Securely handle guest payments and host payouts.

🔐 There’s an arrow between Make Payment and Payment Gateway to depict this connection.
