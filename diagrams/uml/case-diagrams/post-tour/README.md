# Post Tour Use Case Diagram

## Overview
This diagram describes the post-tour activities in the Mountain Tours System, including reviews, ratings, reporting, and administrative oversight.

## Actors

| Actor | Description |
|-------|-------------|
| **User** | Registered user who participated in a tour |
| **Tour Operator** | Business entity that manages tours and views performance metrics |
| **Admin** | System administrator with oversight and compliance responsibilities |

## Use Cases

### User Functions
- **Report Issue** - User reports problems or concerns about a tour
- **Rate & Review Guide** - User provides feedback on their guide
  - `<<include>>` Authenticate
  - `<<include>>` Verify Tour Completion
- **Rate & Review Tour** - User provides feedback on the tour experience
  - `<<include>>` Verify Tour Completion

### Tour Operator Functions
- **Publish Tour Updates** - Tour Operator shares news and updates about tours
  - `<<include>>` Send Notification
- **Verify Guide Credentials** - Tour Operator validates guide certifications and qualifications
- **View Tour Revenue** - Tour Operator views financial performance of their tours
- **View Booking Statistics** - Tour Operator analyzes booking trends and metrics

### Admin Functions
- **Monitor Tour Safety Compliance** - Admin ensures tours meet safety standards
- **Configure System Settings** - Admin manages platform configuration
- **Handle Disputes** - Admin resolves conflicts between users, guides, and operators
- **Generate Reports** - Admin creates system-wide reports and analytics
- **View Booking Statistics** - Admin views platform-wide booking data

## Relationships

### Include Dependencies
- **Rate & Review Guide** includes **Authenticate**, **Verify Tour Completion**
- **Rate & Review Tour** includes **Verify Tour Completion**
- **Publish Tour Updates** includes **Send Notification**
