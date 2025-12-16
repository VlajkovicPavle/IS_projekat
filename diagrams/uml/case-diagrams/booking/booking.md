# Booking Use Case Diagram

## Overview
This diagram describes the tour booking functionality for the Mountain Tours System.

## Actors

| Actor | Description |
|-------|-------------|
| **User** | Registered user who can book and manage tours |
| **Tour Operator** | Business entity that manages tour bookings |
| **Guide** | Tour guide who responds to requests and manages participants |

## Use Cases

### Tour Booking
- **Request Private Tour** - User requests a custom private tour
  - `<<include>>` Authenticate
  - `<<include>>` Check Availability
  - `<<include>>` Send Notification
- **Book Group Tour** - User books a spot on an existing group tour
  - `<<include>>` Authenticate
  - `<<include>>` Check Availability
  - `<<include>>` Send Notification

### Booking Management
- **View My Bookings** - User views their booking history and upcoming tours
- **Reschedule Booking** - User changes the date/time of an existing booking
  - `<<include>>` Send Notification
- **Cancel Booking** - User cancels an existing booking
  - `<<include>>` Send Notification

### Tour Operator Functions
- **View Bookings for Tours** - Tour Operator views all bookings for their tours

### Guide Functions
- **Respond to Tour Request** - Guide accepts or declines private tour requests
- **Manage Participant List** - Guide manages the list of participants for a tour

## Relationships

### Include Dependencies
- **Request Private Tour** includes **Authenticate**, **Check Availability**, **Send Notification**
- **Book Group Tour** includes **Authenticate**, **Check Availability**, **Send Notification**
- **Reschedule Booking** includes **Send Notification**
- **Cancel Booking** includes **Send Notification**
