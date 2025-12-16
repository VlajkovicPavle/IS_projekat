# Pre Tour Use Case Diagram

## Overview
This diagram describes the pre-tour and during-tour activities in the Mountain Tours System, focusing on communication, tracking, and tour preparation.

## Actors

| Actor | Description |
|-------|-------------|
| **User** | Registered user who has booked a tour |
| **Guide** | Tour guide preparing for and conducting the tour |

## Use Cases

### User Functions
- **Track Live Location** - User tracks the guide's real-time location during the tour
  - `<<include>>` Authenticate
- **Communicate with Clients** - User communicates with the guide before/during the tour
  - `<<include>>` Authenticate
  - `<<include>>` Share Live Location
- **View Tour Checklist** - User views preparation checklist for the upcoming tour
  - `<<include>>` Authenticate

### Guide Functions
- **Share Live Location** - Guide shares their real-time location with tour participants
- **View Earnings** - Guide views their earnings and payment history
- **Submit Expenses/Reports** - Guide submits expense reports for reimbursement
- **Upload Tour Photos/Report** - Guide uploads photos and reports from tours
- **Update Tour Status** - Guide updates the current status of an ongoing tour
  - `<<include>>` Send Notification
- **Upload Tour Photos** - Guide uploads photos during or after the tour

### Communication
- **Communicate with Clients** - Bidirectional communication between guide and users
  - `<<include>>` Authenticate
  - `<<include>>` Share Live Location
- **Send Notification** - System sends notifications for status updates

## Relationships

### Include Dependencies
- **Track Live Location** includes **Authenticate**
- **Communicate with Clients** includes **Authenticate**, **Share Live Location**
- **View Tour Checklist** includes **Authenticate**
- **Update Tour Status** includes **Send Notification**
