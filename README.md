# DIU Transport Management System

A transport management system for Daffodil International University (DIU) that lets Students, Faculty, and Staff apply for a virtual transport card, view routes and bus schedules, and submit complaints — while Admins manage buses, drivers, helpers, routes, schedules, and notices.

## Team

| Name | ID | Role |
|---|---|---|
| Ahsan Habib | Mobile App (Android) |
| Sahriar Ekhlas | Backend |
| Katon Chakma | Database |

## Tech Stack

- **Mobile App:** Java + XML (Android)
- **Backend:** Spring Boot (Java)
- **Database:** MySQL / PostgreSQL
- **Authentication:** Spring Security + JWT
- **API Style:** REST (JSON)

## Architecture

3-tier architecture:

```
Mobile App (Java + XML)
      │  HTTP/JSON + JWT
      ▼
Backend API (Spring Boot)
  Controller → Service → Repository
      │
      ▼
Database (MySQL / PostgreSQL)
```

## Roles

| Role | Access |
|---|---|
| Student / Faculty / Staff | Self-register |
| Driver / Helper | Created by Admin |
| Admin | Seeded manually (first admin only) |

## Features

### All Users
- Login / Register
- View & update profile, change password
- View notices
- Submit complaints

### Student / Faculty / Staff
- Apply for transport (Visa / MasterCard / bKash — demo payment)
- Virtual Transport Card (name, DIU ID, department, semester, year, valid until, status)
- View routes
- View bus schedule

### Driver / Helper
- View assigned bus, route, and schedule

### Admin
- Dashboard overview (users, buses, routes, complaints)
- Manage users, drivers, helpers
- Manage buses (create/update/delete, assign driver & helper)
- Manage routes and schedules
- Manage notices
- View and reply to complaints

## Getting Started

1. Clone the repository
   ```bash
   git clone https://github.com/Md-A-Habib/DIU_Transport_App.git
   ```
2. Open the project in Android Studio
3. Let Gradle sync finish
4. Update the backend base URL in the app's network config
5. Run the app on an emulator or physical device

## Build Order

1. Database — create tables (users, drivers, helpers, buses, bus_routes, bus_schedules, transport_registrations, notices, complaints)
2. Backend — Auth (register/login/JWT) → Admin management → Buses/Routes/Schedules → Transport Registration → Notices & Complaints
3. Mobile App — Login/Register → role-based Home → wire each screen to its API

## License

This project is developed for academic purposes at Daffodil International University.
