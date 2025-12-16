# Account & Registration Use Case Diagram

## Overview
This diagram describes the account management and registration functionality for the Mountain Tours System.

## Actors

| Actor | Description |
|-------|-------------|
| **User** | Unauthenticated visitor who can register for an account |
| **Registered User** | Base authenticated user with basic system access |
| **Admin** | System administrator with full management capabilities |
| **Tour Operator** | Business entity that manages tours and guides |
| **Guide** | Specialized user who conducts tours (extends Registered User) |

## Use Cases

### Authentication
- **Authenticate** - All users must authenticate to access protected features

### Registration & Approval
- **Register** - Users can create a new account in the system
- **Approve Guide Registration** - Admin reviews and approves guide applications
- **Approve Tour Operator Registration** - Admin reviews and approves tour operator applications
- **Reject/Suspend Account** - Admin can reject new registrations or suspend existing accounts

### Profile Management
- **Manage Profile** - Registered Users, Tour Operators, and Guides can update their profile information
- **Save Favorite Tours/Guides** - Registered Users can bookmark preferred tours and guides

### User Administration
- **Manage Users** - Admin and Tour Operators can manage user accounts within their scope

## Relationships

- **User** generalizes to **Registered User** (inheritance)
- **Registered User** generalizes to **Guide** (inheritance)
- All authenticated actions require the **Authenticate** use case
