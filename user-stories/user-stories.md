# 📘 User Stories for Airbnb Clone Backend

---

## 🧍‍♂️ 1. User Registration and Profile Management

### **User Story**
As a new user, I want to be able to register as a guest or host using my email or social login (e.g., Google), so that I can securely access the platform’s features and personalize my profile.

### **Acceptance Criteria**
- User can choose to register as Guest or Host  
- Registration supports OAuth via Google/Facebook  
- On success, user can update profile details like photo, contact info, and preferences

---

## 🏘️ 2. Host Property Listing Management

### **User Story**
As a host, I want to be able to add, update, or remove property listings, so that I can manage the availability and details of my rentals.

### **Acceptance Criteria**
- Host can fill in title, description, price, amenities, and upload images  
- Host can update listing details or remove a listing  
- Admin gets notified for new listing approval

---

## 🔍 3. Guest Property Search and Booking

### **User Story**
As a guest, I want to search for available properties using filters like location, price, and amenities, so that I can find accommodations that match my needs and make a reservation.

### **Acceptance Criteria**
- Search supports filters: price, amenities, location, dates  
- Property details are accessible via listings  
- Guest can select a property and create a booking

---

## 💳 4. Secure Payments and Payouts

### **User Story**
As a guest, I want to make secure payments for my bookings, and as a host, I want to receive payouts after successful stays, so that transactions are seamless and automated.

### **Acceptance Criteria**
- Guest can pay via Stripe or PayPal  
- Payment Gateway processes and verifies transactions  
- Hosts are automatically credited after the booking is completed

---

## 🌟 5. Review System and Notifications

### **User Story**
As a guest, I want to leave a review after a stay, and as a host, I want to respond to reviews, so that feedback is transparent. Also, I want to receive real-time notifications for bookings and updates.

### **Acceptance Criteria**
- Review form available to guests post-booking  
- Host can reply once per guest review  
- Both actors receive booking confirmation, payment status, and cancellation updates via email or in-app alert
