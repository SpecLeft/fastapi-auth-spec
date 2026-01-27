# Authentication Service PRD

## Overview
A minimal authentication service using FastAPI, supporting user registration, JWT login, and protected route access.

## Features

### Registration
**As a** new user
**I want to** register with a username and password
**So that** I can access the system

- **Scenario: Successful Registration**
  - Given a new user "alice" with password "secret"
  - When they register
  - Then the user is created successfully
  - And the response status is 201

- **Scenario: Duplicate Username**
  - Given an existing user "alice"
  - When a new user tries to register as "alice"
  - Then the registration fails
  - And the response status is 400

### Login
**As a** registered user
**I want to** log in with my credentials
**So that** I can obtain an access token

- **Scenario: Successful Login**
  - Given a user "alice" with password "secret"
  - When they log in with "alice" and "secret"
  - Then a valid access token is returned
  - And the response status is 200

- **Scenario: Invalid Password**
  - Given a user "alice" with password "secret"
  - When they log in with "alice" and "wrongpass"
  - Then the login fails
  - And the response status is 401

### Protection
**As a** system owner
**I want to** protect sensitive endpoints
**So that** only authenticated users can access them

- **Scenario: Access Protected Route**
  - Given a valid access token for "alice"
  - When they access the protected endpoint
  - Then the request is successful
  - And the response contains the username "alice"

- **Scenario: Access Without Token**
  - Given no access token
  - When they access the protected endpoint
  - Then the request is denied
  - And the response status is 401
