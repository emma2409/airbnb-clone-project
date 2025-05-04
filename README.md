# airbnb-clone-project

The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security.

# Team Roles

Backend Developer: Builds and maintains server-side logic, APIs, databases, and application integration 
Database Administrator: Designs, manages, and optimizes databases for performance, security, and scalability
QA Engineer / Tester: Tests backend systems for bugs, performance, and security issues
System Architect: Designs the system architecture including microservices, data flow, and tech stack decisions.
DevOps Engineer: Manages deployment pipelines, cloud infrastructure, and ensures system reliability
Project Manager: Oversees the project timeline, team coordination, and stakeholder communication.

# Technology Stack

Django: A high-level Python web framework used for building the RESTful API.
Django REST Framework: Provides tools for creating and managing RESTful APIs.
PostgreSQL: A powerful relational database used for data storage.
GraphQL: Allows for flexible and efficient querying of data.
Celery: For handling asynchronous tasks such as sending notifications or processing payments.
Redis: Used for caching and session management.
Docker: Containerization tool for consistent development and deployment environments.
CI/CD Pipelines: Automated pipelines for testing and deploying code changes.

# Database Design

The key entities required for the project
1. User: Represents both guests and hosts.

Important Fields:user_id (Primary Key), name, email, user_type (guest or host), created_at

Relationships: 
A user can host multiple properties.
A user can make multiple bookings.
A user can write multiple reviews.

2. Property: Represents a rental listing.

Important Fields:
property_id (Primary Key)
host_id (Foreign Key → User)
title
location
price_per_night
created_at

Relationships:
A property belongs to a host (user).
A property can have multiple bookings.
A property can have multiple reviews.
A property can have many images.

3. Booking: Represents a reservation by a guest.

Important Fields:
booking_id (Primary Key)
guest_id (Foreign Key → User)
property_id (Foreign Key → Property)
check_in_date
check_out_date
total_price
booking_status (confirmed, cancelled, etc.)

Relationships:
A booking is made by a guest (user).
A booking is for one property.

4. Review: Represents feedback left by a guest after a stay.

Important Fields:
review_id (Primary Key)
property_id (Foreign Key)
user_id (Foreign Key → User)
rating (1–5)
comment
created_at

Relationships:
A review is written by a user.
A review belongs to a property.

5. Payment: Tracks transactions for bookings.

Important Fields:
payment_id (Primary Key)
booking_id (Foreign Key)
amount
payment_method
payment_status

Relationships:
A payment is linked to a booking.
