#Crossed Backend

Django REST API for the Crossed dating app.

##Overview

This backend handles user registration and authentication. It is designed to communicate with the React frontend.

##Features

- **Registration:** Creates new user accounts and stores additional registration details.
- **Login:** Authenticates users using their email and password.
- **JWT Authentication:** Generates access and refresh tokens.
- **Token Refresh:** Allows users to obtain new access tokens.
- **Logout:** Blacklists refresh tokens to prevent further use.

##API Endpoints

Method| Endpoint| Description
POST| "/api/register/"| Register a new user
POST| "/api/token/"| Log in and receive JWT tokens
POST| "/api/token/refresh/"| Refresh authentication tokens
POST| "/api/logout/"| Log out and blacklist a refresh token

##Installation

Install the required packages:

///pip install -r requirements.txt

Apply database migrations:

/// python manage.py migrate

Start the Django development server:

/// python manage.py runserver

##Important Notes

- Login requires an email address and password.
- Protected endpoints require an access token.
- The logout endpoint requires authentication and a refresh token.
- The refresh token is blacklisted during logout.
- Access tokens remain valid until they expire.
- The Django secret key must be configured locally using the "DJANGO_SECRET_KEY" environment variable.