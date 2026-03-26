# Login Flow Project – Requirements

The system will allow registered users to log in using a registered email address and corresponding valid password to securely access their account. This document defines the expected functionality, behaviour, and constraints of the login process.

## 1. Overview

The system will allow registered users to log in using a registered email address and corresponding valid password to securely access their account. This document will define the expected functionality,behaviour, and constraints of the login process.

## 2. Functional Requirements

### 2.1 Login
- 2.1.1: Users must enter a registered email address and corresponding valid password.
- 2.1.2: Clicking the Login button triggers credential validation.
- 2.1.3: If credentials are valid and the account is active, the user is redirected to their dashboard.

### 2.2 Invalid Login
- 2.2.1: If the credentials do not match a registered email-password combination:
  - 2.2.1.1: Display the message “Invalid email or password.”
  - 2.2.1.2: User remains on the login page.

### 2.3 Empty Fields
- 2.3.1: When submitting with empty email or password fields the system shall display a relevant
validation message (see table).

#### Empty Field Validation Message Table

|             Scenario            |                Message                       |  
|---------------------------------|----------------------------------------------|
| Missing email                   | Please enter your email address              |
| Missing password                | Please enter your password                   |
| Both email and password missing | Please enter your email address and password |

### 2.4 Forgot Password
- 2.4.1: Users can click Forgot Password to reset their password.
- 2.4.2: Users must enter their registered email.
- 2.4.3: The system sends a password reset email with a secure link.

### 2.5 Password Reset
- 2.5.1: Clicking the link in the reset email allows the user to set a new password.
- 2.5.2: The new password shall be a minimum of 8 characters and include at least 1 letter and 1
number.

### 2.6 Session Management
- 2.6.1: Users remain logged in until:
  - 2.6.1.1: They log out
  - 2.6.1.2: Session timeout occurs (e.g., 30 minutes of inactivity)

### 2.7 Account Access Restrictions
- 2.7.1: Users with valid credentials shall be denied access if the account is locked, disabled, or inactive.
- 2.7.2: The system shall display the error message “Your account is locked. Please contact
support.”

### 3 Non-Functional Requirements
- 3.1: Performance: Login action completes within 2 seconds under normal load.
- 3.2: Security:
  - 3.2.1: Password fields must be masked.
  - 3.2.2: No sensitive information should be exposed in error messages.

### 4 Assumptions
- 4.1: Users have pre-registered accounts.
- 4.2: Email service for password reset is operational.
- 4.3: Email addresses are validated for correct form at registration

### 5 Out of Scope
- 5.1: Social login (Google, Facebook)
- 5.2: Multi-factor authentication
- 5.3: Account setup
