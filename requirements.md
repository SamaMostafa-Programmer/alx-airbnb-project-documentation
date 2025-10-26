🏠 Airbnb Clone – Requirement Specifications
1. User Management

Endpoints:

POST /api/users/register → Register a new user

POST /api/users/login → User login

GET /api/users/:id → Get user profile
Validation Rules:

Email must be unique and valid format (name@email.com)

Password ≥ 8 characters

All fields required

Performance Expectations:

Registration/Login response < 2 seconds

Database lookup optimized with user index
------------------------------------------------------
2. Property / Listing Management

Endpoints:

POST /api/listings → Create new listing

GET /api/listings → Get all listings

GET /api/listings/:id → Get single listing

Validation Rules:

Title, location, and price are required

Price must be a positive number

HostId must exist in Users table

Performance Expectations:

Fetch all listings in < 3 seconds

API supports pagination (limit, skip)
------------------------------------------------------
3. Booking System

Endpoints:

POST /api/bookings → Create a booking

GET /api/bookings/:userId → Get all bookings for a user

DELETE /api/bookings/:id → Cancel booking

Validation Rules:

Dates must be valid and in the future

Listing must not be double-booked

User must be authenticated

Performance Expectations:

Booking confirmation < 2 seconds

Database ensures atomic transactions
--------------------------------------------------------
4. Review System

Endpoints:

POST /api/reviews → Add review

GET /api/reviews/:listingId → Get reviews for listing

Validation Rules:

Rating: 1–5 only

Comment: optional, max 300 chars

User must have booked before reviewing

Performance Expectations:

Reviews load < 1 second per listing
------------------------------------------------------
NOTES:

All responses use JSON format

All endpoints secured using JWT tokens

Database used: MongoDB / PostgreSQL

API follows RESTful design principles
