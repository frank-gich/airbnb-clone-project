# airbnb-clone-project
🧑‍💻 Team Roles
1. Backend Developer
Responsible for developing and maintaining the server-side logic, APIs, and application architecture. Ensures efficient data flow between the frontend, database, and third-party services.

2. Frontend Developer
Creates and maintains the user interface (UI) and user experience (UX) of the application. Works closely with backend developers to integrate APIs and provide a responsive, accessible design.

3. Database Administrator (DBA)
Designs, implements, and manages the project's data storage solutions. Ensures data integrity, security, and performance through efficient schema design, indexing, and regular backups.

4. DevOps Engineer
Manages infrastructure, CI/CD pipelines, and deployment processes. Ensures code is deployed reliably and systems are monitored, scalable, and secure.

5. Project Manager (PM)
Coordinates project activities, manages the team schedule, and ensures timely delivery of milestones. Acts as a liaison between the development team and stakeholders.

6. QA Engineer
Writes and executes test plans, both automated and manual, to identify bugs and ensure the application meets quality standards before deployment.

7. UI/UX Designer
Designs the application's interface and ensures the product is user-friendly and aligned with the project's goals and branding.

🛠️ Technology Stack
1. Django
A high-level Python web framework used for building secure and scalable web applications. In this project, Django is used to build RESTful APIs and manage backend logic.

2. PostgreSQL
An advanced open-source relational database management system. Used to store and manage structured data with strong support for ACID compliance and powerful querying capabilities.

3. GraphQL
A query language for APIs that allows clients to request exactly the data they need. Enables efficient and flexible communication between frontend and backend services.

4. React (if applicable)
A JavaScript library for building fast and interactive user interfaces. Used in the frontend to provide a dynamic and responsive user experience.

5. Docker (if applicable)
A containerization platform that simplifies deployment and environment management by packaging the application with all its dependencies.

6. Nginx (if applicable)
A high-performance web server and reverse proxy. Used to serve static files and route API requests efficiently.

🗃️ Database Design
The database schema is designed to support core functionalities such as property listings, user bookings, reviews, and payment processing. Below are the key entities and their relationships.

1. Users
Represents individuals using the platform (guests or hosts).

Fields:

id: Unique identifier

name: Full name

email: Email address (unique)

password_hash: Encrypted password

role: User type (e.g., guest, host)

Relationships:

A user can own multiple properties

A user can make multiple bookings

A user can write multiple reviews

2. Properties
Represents real estate listings added by hosts.

Fields:

id: Unique identifier

owner_id: References the user who owns the property

title: Property name or headline

description: Detailed information

location: City, address, or coordinates

Relationships:

A property belongs to one user (host)

A property can have many bookings and reviews

3. Bookings
Tracks reservation details between guests and hosts.

Fields:

id: Unique identifier

user_id: References the guest who booked

property_id: References the booked property

start_date: Check-in date

end_date: Check-out date

Relationships:

A booking belongs to one user (guest)

A booking belongs to one property

4. Reviews
Allows users to review properties.

Fields:

id: Unique identifier

user_id: References the reviewer

property_id: References the property reviewed

rating: Score (e.g., 1–5)

comment: Review text

Relationships:

A review belongs to one user

A review belongs to one property

5. Payments
Handles financial transactions related to bookings.

Fields:

id: Unique identifier

booking_id: References the related booking

amount: Total amount paid

status: Payment status (e.g., completed, failed)

payment_date: Timestamp of transaction

Relationships:

A payment belongs to one booking


Entity Relationships Summary
🧑 User → owns many → 🏠 Properties

🧑 User → makes many → 📅 Bookings

🏠 Property → has many → 📅 Bookings

🧑 User → writes many → ✍️ Reviews

🏠 Property → has many → ✍️ Reviews

📅 Booking → has one → 💳 Payment
