---
title: "RoomRent Web Service"
date: 2024-01-01
tags: ["Laravel", "PHP", "REST API", "mobile backend", "Android", "iOS", "repository pattern"]
author: ["Manita Pote"]
description: "A RESTful web service built with Laravel and PHP serving as the backend for a room rental mobile application."
summary: "A Laravel-based REST API backend for a cross-platform room rental app, enabling users to list, search, and request rooms for rent on Android and iOS."
cover:
    image: "roomrent.png"
    alt: "RoomRent Web Service"
    relative: true
editPost:
    URL: "https://github.com/manitapote/RoomRent-webservice"
    Text: "GitHub"
---

---

##### Overview

RoomRent is a RESTful web service built with Laravel and PHP, designed as the backend for a cross-platform mobile application on Android and iOS. The API follows the **Repository Design Pattern**, decoupling the business logic from data access layers for clean, maintainable, and testable code. It enables users to list available rooms for rent and submit rental requests, connecting landlords and tenants through a scalable backend architecture.

---

##### Architecture

The project follows the **Repository Design Pattern**:

- **Controller** — handles HTTP requests and responses
- **Repository Interface** — defines the contract for data operations
- **Repository Implementation** — handles all database queries via Eloquent ORM
- **Service Layer** — contains business logic, sits between controller and repository

This separation of concerns makes the codebase easy to test, extend, and maintain.

---

##### Features

- 🏠 List and browse available rooms for rent
- 📱 RESTful API endpoints for Android and iOS clients
- 🔐 User authentication and authorization
- 📋 Room request and booking management
- 🔍 Search and filter rooms by location and price
- 👤 Separate roles for landlords and tenants
- 🏗️ Repository design pattern for clean architecture

---

##### Tech Stack

- **Language:** PHP
- **Framework:** Laravel
- **Database:** MySQL
- **API:** RESTful JSON API
- **Architecture:** Repository Design Pattern
- **Auth:** Laravel Sanctum / Passport

---

##### Usage

```bash
git clone https://github.com/manitapote/RoomRent-webservice
cd RoomRent-webservice
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
```

---

##### Code

+ [GitHub Repository](https://github.com/manitapote/RoomRent-webservice)