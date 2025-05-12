#   Airbnb Clone - Backend User Stories Documentation

##  📘 Introduction

This project is a **backend system for an Airbnb clone**, focused on building a RESTful API that supports core functionalities for **Guests** and **Hosts**. The API enables user authentication, property listing management, booking, and reviews — all tailored to a smooth short-term rental experience.

This README outlines the **functional user stories** that define expected behavior for guests and hosts, serving as a foundation for backend development.

---

##  👤 Guest User Stories

1.  **Listing Management:**
    * **Story:** As a Host, I would like to be able to add a property listing with details such as title, description, location, price, amenities, and availability, so that potential guests can view and book my property.
    * **Details:** This feature allows hosts to create detailed property listings.  Key data includes:
        * Title and Description: To provide an overview of the property.
        * Location: To specify where the property is situated.
        * Price: To set the rental price.
        * Amenities: To list available features (e.g., Wi-Fi, parking).
        * Availability: To define when the property can be booked.

2.  **User Management:**
    * **Story**: As a User, I would like to be able to register an account with secure authentication (JWT, OAuth) in order to access the features of the platform, such as booking properties or listing my own.
    * **Details**: This feature enables user registration and secure login.
        * Registration: Users can create accounts providing necessary details.
        * Authentication:  Secure authentication using JWT (JSON Web Tokens) and OAuth (e.g., Google, Facebook) will be implemented.

3.  **Booking Management:**
    * **Story**: As a Guest, I would like to be able to create a booking for a property on specified dates, and the system should prevent double bookings, so that I can secure my reservation.
    * **Details**: This feature allows guests to book properties.
        * Booking Creation: Guests can select a property and specify dates.
        * Date Validation: The system will validate dates to prevent double bookings.

4.  **Reviews and Ratings:**
    * **Story**: As a Guest, I would like to be able to leave a review and rating for a property where I have stayed, so that I can share my experience with other potential guests.
        * **Details**: This feature enables guests to provide feedback on their stay.
            * Review Submission: Guests can write reviews and provide ratings.
            * Booking Association: Reviews will be linked to specific bookings.

---

##  🏠 Host User Stories

1.  **Listing Management:**
    * **Story:** As a Host, I would like to be able to add a property listing with details such as title, description, location, price, amenities, and availability, so that potential guests can view and book my property.
    * **Details:** This feature allows hosts to create and manage property listings.
        * Add Listing: Hosts can create new listings with property details.
        * Edit/Delete Listings: Hosts can modify or remove their listings.

2.  **Booking Management:**
     * **Story:** As a Host, I would like to be able to manage bookings for my properties, including viewing booking requests, confirming or rejecting them, and setting booking availability.
     * **Details**:  This feature enables hosts to manage their property reservations.
         * View Bookings:  Hosts can see details of pending and confirmed bookings.
         * Confirm/Reject: Hosts can approve or decline booking requests.
         * Set Availability:  Hosts can specify when their properties are available.

---
## 🔒 Authentication & Roles

The system will implement secure authentication and role-based access control to ensure that users can only access the features appropriate to their roles (Guest, Host, Administrator).

* **Authentication:**
    * Users will authenticate using email and password.
    * The system will support JWT (JSON Web Tokens) for secure session management.
    * OAuth (e.g., Google, Facebook) will be integrated for convenient login.

* **Roles:**
    * **Guest:** Can search for properties, book properties, manage bookings, and leave reviews.
    * **Host:** Can list properties, manage listings, and manage bookings for their properties.
    * **Administrator:** Can manage all users, listings, bookings, and payments in the system.
