
# 🔧 Requirement Specification

## 1. User Authentication

### Functional Requirements

- Users should be able to register, log in, and log out securely.
- JWT tokens should be used for authenticated sessions.
- Different roles (guest, host, admin) should determine access levels.

### Technical Requirements

#### API

- **Endpoint**: `POST /auth/login`

- **Input**:
```json
{
  "email": "user@example.com",
  "password": "userPassword123"
}
```

- **Output**:
```json
{
  "token": "JWT-token",
  "user_id": "uuid",
  "message": "Login successful"
}
```

- **Validation**
  - Password must be at least 8 characters.
  - Email must be valid and registered.

- **Error**
  - `401 Unauthorized`: Invalid email or password.
  - `422 Unprocessable`: Missing credentials.

---

## 2. Property Management

### Functional Requirements

- Hosts should be able to create, update, and delete their property listings.
- Listings should include details like title, price, location, and amenities.

### Technical Requirements

#### API

- **Endpoint**: `POST /properties`

- **Input**:
```json
{
  "host_id": "uuid",
  "title": "Cozy Apartment",
  "description": "A lovely flat in Paris",
  "location": "Paris, France",
  "price": 90.00,
  "amenities": ["Wi-Fi", "Heating", "Kitchen"]
}
```

- **Output**:
```json
{
  "property_id": "uuid",
  "message": "Property created successfully"
}
```

- **Validation**
  - Price must be a number and greater than zero.
  - Title, location, and host_id are required.

- **Error**
  - `403 Forbidden`: Unauthorized host.
  - `422 Unprocessable`: Invalid or missing data.

---

## 3. Booking System

### Functional Requirements

- Guests should be able to book available properties for specific dates.
- Double bookings should be prevented.
- Bookings can be canceled by users or hosts.

### Technical Requirements

#### API

- **Endpoint**: `POST /bookings`

- **Input**:
```json
{
  "user_id": "uuid",
  "property_id": "uuid",
  "start_date": "2025-08-01",
  "end_date": "2025-08-05"
}
```

- **Output**:
```json
{
  "booking_id": "uuid",
  "status": "confirmed",
  "message": "Booking successful"
}
```

- **Validation**
  - Dates must be valid and not overlap with existing bookings.
  - End date must be after start date.

- **Error**
  - `409 Conflict`: Property not available for selected dates.
  - `422 Unprocessable`: Invalid or missing fields.

---

🔐 **Note**: All endpoints that modify data must be secured using JWT authorization headers:  
`Authorization: Bearer <token>`
