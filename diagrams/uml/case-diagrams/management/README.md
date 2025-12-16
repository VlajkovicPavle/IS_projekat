# Tour Management & Assignment Use Case Diagram

## Overview
This diagram describes the tour management and guide assignment functionality for the Mountain Tours System.

## Actors

| Actor | Description |
|-------|-------------|
| **Guide** | Tour guide who manages their availability and assigned tours |
| **Tour Operator** | Business entity that creates tours and assigns guides |

## Use Cases

### Guide Functions
- **View All My Tours** - Guide views all tours they are assigned to
- **Cancel Tour** - Guide cancels a tour they are leading
- **Manage Availability Calendar** - Guide sets their available dates and times
  - `<<include>>` Authenticate
- **Respond to Assignment** - Guide accepts or declines tour assignments
  - `<<include>>` Authenticate
  - `<<include>>` Send Notification
- **View Assigned Group Tours** - Guide views group tours assigned to them

### Tour Operator Functions
- **Set Tour Schedule & Capacity** - Tour Operator defines when tours run and maximum participants
- **Manage Group Tours** - Tour Operator creates and manages group tour offerings
- **Assign Guide to Tour** - Tour Operator assigns available guides to specific tours
  - `<<include>>` Send Notification
- **View Assignment Status** - Tour Operator monitors guide assignment statuses
- **Create Group Tour** - Tour Operator creates new group tour offerings

### Shared Functions
- **Reschedule Tour** - Both Guide and Tour Operator can reschedule tours

## Relationships

### Include Dependencies
- **Manage Availability Calendar** includes **Authenticate**
- **Respond to Assignment** includes **Authenticate**, **Send Notification**
- **Assign Guide to Tour** includes **Send Notification**
