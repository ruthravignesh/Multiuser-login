# Django User Registration and Authentication System

## Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Tech Stack](#tech-stack)
4. [Prerequisites](#prerequisites)
5. [Installation](#installation)
6. [Usage](#usage)
7. [Project Structure](#project-structure)
8. [Database Schema](#database-schema)
9. [Security Features](#security-features)
10. [API Endpoints](#api-endpoints)
11. [Future Enhancements](#future-enhancements)
12. [Adding Images to Documentation](#adding-images-to-documentation)
13. [Contributing](#contributing)
14. [License](#license)

---

## Introduction

This is a Django-based backend application designed for user registration, authentication, and role-based access control. Users can register, log in, and access features based on their assigned roles (e.g., admin, editor, viewer). The system ensures data security and provides a user-friendly interface.

---

## Features

- User Registration with validation
- Secure Authentication (password hashing)
- Role-based access control (e.g., admin, user, editor)
- Database storage for user details
- Customizable user roles
- API support for integration
- High security with Django’s built-in and custom measures

---

## Tech Stack

- **Framework:** Django (Python)
- **Database:** SQLite (default) / PostgreSQL / MySQL (configurable)
- **Frontend:** Django templates (default; customizable for integration)
- **Security:** Django Authentication, CSRF Protection, Password Hashing
- **Other Tools:** Django Rest Framework (optional for API)

---

## Prerequisites

- Python 3.8 or higher
- Django 4.x or higher
- pip (Python package manager)

---

## Installation

### Clone the Repository
```bash
$ git clone https://github.com/yourusername/django-user-auth-system.git
$ cd django-user-auth-system
```

### Create a Virtual Environment
```bash
$ python -m venv venv
$ source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### Install Dependencies
```bash
$ pip install -r requirements.txt
```

### Set Up the Database
```bash
$ python manage.py makemigrations
$ python manage.py migrate
```

### Create a Superuser
```bash
$ python manage.py createsuperuser
```
Follow the prompts to set up admin credentials.

### Run the Development Server
```bash
$ python manage.py runserver
```
Access the application at `http://127.0.0.1:8000/`.

---

## Usage

1. **User Registration**: New users can register through the `/register/` page.
2. **User Login**: Users can log in via the `/login/` page.
3. **Role Management**: Assign roles to users in the Django Admin Panel.
4. **Role-Based Access**: Define permissions for each role in views and templates.

---

## Project Structure

```
├── django-user-auth-system/
│   ├── manage.py
│   ├── requirements.txt
│   ├── db.sqlite3
│   ├── project_name/
│   │   ├── settings.py
│   │   ├── urls.py
│   │   ├── wsgi.py
│   │   └── asgi.py
│   ├── auth_app/
│   │   ├── migrations/
│   │   ├── templates/
│   │   │   ├── registration.html
│   │   │   ├── login.html
│   │   │   ├── dashboard.html
│   │   │   └── admin_dashboard.html
│   │   ├── models.py
│   │   ├── views.py
│   │   ├── urls.py
│   │   └── forms.py
```

---

## Database Schema

**User Model** (Customizable using `AbstractUser`):

| Field         | Type         | Description                        |
|---------------|--------------|------------------------------------|
| id            | Integer      | Primary Key                       |
| username      | String       | Unique identifier                 |
| email         | EmailField   | User's email address              |
| password      | String       | Hashed password                   |
| role          | String       | Role of the user (admin, editor)  |
| date_joined   | DateTime     | Timestamp for user registration   |

---

## Security Features

- Password hashing with Django’s `PBKDF2PasswordHasher`
- CSRF Protection for forms
- Secure session management
- User roles and permission-based access

---

## API Endpoints (if using Django Rest Framework)

### Authentication
- **POST** `/api/login/` - User login
- **POST** `/api/register/` - User registration
- **GET** `/api/logout/` - User logout

### User Management
- **GET** `/api/users/` - List all users (admin-only)
- **PUT** `/api/users/<id>/` - Update user details
- **DELETE** `/api/users/<id>/` - Delete a user (admin-only)

---

## Future Enhancements

- Integrate JWT authentication for API security.
- Add multi-factor authentication (MFA).
- Create a user-friendly frontend with React or Angular.
- Enable email verification during registration.
- Implement audit logs for user activity.

---




![Frontend Page](https://github.com/user-attachments/assets/2742578e-ded2-4355-977f-1a60f8278a7d)



![Registration Page](https://github.com/user-attachments/assets/e1cec3f7-24cb-4f00-a2ad-51e765ca62cf)


![Screenshot 2024-11-28 123540](https://github.com/user-attachments/assets/4cc11a48-f261-42a1-a053-e59b7e2becf2)


---

## Contributing

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Commit your changes and push to the branch.
4. Submit a pull request.

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

