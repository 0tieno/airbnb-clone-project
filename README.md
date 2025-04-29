# airbnb-clone-project

## Team Roles
In this project, each team member plays a crucial role in ensuring successful delivery. Below are the primary roles and their responsibilities:

### Backend Developer
Responsible for building and maintaining the server-side logic of the application. This includes writing APIs, integrating databases, and ensuring secure and scalable application behavior.

### Frontend Developer
Focuses on developing the user interface (UI) and user experience (UX). Converts designs into functional and responsive web pages using HTML, CSS, and JavaScript frameworks.

### Database Administrator (DBA)
Ensures the proper setup, configuration, and maintenance of the project’s databases. Manages data backups, optimizes queries, and ensures data integrity and security.

### QA Engineer
Designs and executes test plans to identify bugs and ensure the software meets quality standards. Works closely with developers to automate testing and validate new features.

### DevOps Engineer
Manages CI/CD pipelines, automates deployments, monitors system performance, and ensures infrastructure is scalable and reliable.

### Project Manager
Oversees the project timeline, task allocation, and team communication. Ensures the project stays on schedule and within scope while meeting stakeholder expectations.

### Technical Writer
Creates and maintains technical documentation such as user guides, API docs, and the README file itself to ensure clarity and usability.

## Technology Stack
Below is a list of technologies used in this project, along with a brief explanation of their roles:

1. Django: A high-level Python web framework used for building secure and scalable backend services and RESTful APIs.

2. PostgreSQL: A powerful, open-source relational database management system used to store and manage structured application data.

3. GraphQL: A query language for APIs that allows clients to request exactly the data they need, improving efficiency in client-server communication.

4. Docker: A containerization platform that packages the application and its dependencies into containers to ensure consistent environments across development, testing, and production.

5. Nginx: A web server used as a reverse proxy to handle incoming requests and serve static files efficiently.

6. Gunicorn: A Python WSGI HTTP server that serves the Django application in a production setting.

7. Redis: An in-memory data store used for caching and message brokering to improve application performance and support background tasks.

8. Celery: A task queue used with Django and Redis for handling asynchronous background tasks like email sending or scheduled jobs.

9. Git: A version control system used to track changes in source code and facilitate collaboration between team members.

## 🗄️ Database Design

### Key Entities and Their Fields

#### **User**
- `id`
- `username`
- `email`
- `password_hash`
- `role` (guest, host, admin)

#### **Property**
- `id`
- `title`
- `description`
- `location`
- `price_per_night`
- `owner_id` (foreign key to User)

#### **Booking**
- `id`
- `user_id` (foreign key to User)
- `property_id` (foreign key to Property)
- `start_date`
- `end_date`

#### **Review**
- `id`
- `user_id` (foreign key to User)
- `property_id` (foreign key to Property)
- `rating`
- `comment`

#### **Payment**
- `id`
- `booking_id` (foreign key to Booking)
- `amount`
- `payment_status`
- `payment_method`

### Relationships

- A user can list multiple properties.
- A user can book multiple properties.
- A booking is linked to one property and one user.
- A review is made by a user for a specific property.
- A payment is tied to a single booking.

---

## ✨ Feature Breakdown

### Main Features of the Airbnb Clone Project

- **User Management**  
  Allows users to register, log in, manage profiles, and view booking history.

- **Property Management**  
  Hosts can add, edit, and delete property listings with descriptions, images, and availability.

- **Booking System**  
  Enables guests to browse listings, make bookings, and check availability based on dates.

- **Review System**  
  Guests can leave reviews and ratings after their stay, helping maintain service quality.

- **Payment Integration**  
  Secure and reliable payments are processed for bookings, with receipts and status updates.

---

## 🔒 API Security

### Security Measures to Protect the API and User Data

- **Authentication**  
  Verifies user identity via tokens (e.g., JWT) to restrict access to protected routes.

- **Authorization**  
  Ensures users can only access or modify resources they own or are permitted to use.

- **Rate Limiting**  
  Prevents abuse by limiting the number of requests a user can make in a given time.

- **Input Validation**  
  Guards against SQL injection, XSS, and other malicious input attempts.

- **Data Encryption**  
  Sensitive data like passwords and payment details are encrypted during transmission and storage.

### Why It's Important

- Protects user data and privacy.  
- Prevents fraudulent transactions and unauthorized access.  
- Builds trust and maintains platform integrity.

---

## 🚀 CI/CD Pipeline

### Overview

**CI/CD (Continuous Integration/Continuous Deployment)** is a development practice that helps automate testing and deployment processes.

- **CI** ensures that every change pushed to the codebase is automatically tested.
- **CD** automates deployment to staging/production environments after successful tests.

### Tools Used

- **GitHub Actions**: Automates testing, building Docker containers, and deployment.  
- **Docker**: Ensures consistent environments from development to production.  
- **Heroku/AWS/Azure (optional)**: Cloud hosting for deployed applications.

### Why It Matters

- Speeds up development cycles.  
- Reduces bugs in production.  
- Encourages continuous delivery of new features.

