# Feature: Auth Service

## Scenarios

### Scenario: Successful Registration
priority: high

- Given a new user "alice" with password "secret"
- When they register
- Then the user is created successfully
- And the response status is 201

### Scenario: Duplicate Username
priority: medium

- Given an existing user "alice"
- When a new user tries to register as "alice"
- Then the registration fails
- And the response status is 400

### Scenario: Successful Login
priority: high

- Given a user "alice" with password "secret"
- When they log in with "alice" and "secret"
- Then a valid access token is returned
- And the response status is 200

### Scenario: Invalid Password
priority: medium

- Given a user "alice" with password "secret"
- When they log in with "alice" and "wrongpass"
- Then the login fails
- And the response status is 401

### Scenario: Access Protected Route
priority: high

- Given a valid access token for "alice"
- When they access the protected endpoint
- Then the request is successful
- And the response contains the username "alice"

### Scenario: Access Without Token
priority: high

- Given no access token
- When they access the protected endpoint
- Then the request is denied
- And the response status is 401
