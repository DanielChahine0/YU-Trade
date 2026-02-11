
# YU-Trade

YU-Trade is an online marketplace for the York University community to buy and sell used items (clothing, books, school supplies, and more). The goal is to reduce waste through reuse and make essential supplies more affordable for students.

## What Problem Does This Solve?

- **Reduces waste** by encouraging recycling, reuse, and upselling within the York University community.
- **Improves affordability** by enabling students to access lower-cost supplies.
- **Keeps the marketplace relevant and safer** by restricting access to verified York University members.

## Core Features / Requirements

- User registration and login with **York University email verification** (must be `@my.yorku.ca` or `@yorku.ca`).
- Create item listings with:
	- title
	- description
	- price
	- images
- Browse and view listings posted by other users.
- Product-specific private messaging between buyers and sellers.
- Basic database persistence for users, listings, and messages.

## Optional Features

- Search and filtering of listings.
- User profile enhancements.
- UI/UX improvements and/or performance optimizations.

## Architecture

YU-Trade follows a **monolithic web architecture**:

- **Frontend:** React
- **Backend:** a single Python backend exposing REST APIs
- **Database:** SQLite

The backend encapsulates the core application logic, including authentication, listing management, and private messaging. This monolithic approach reduces integration overhead and simplifies deployment, which fits a small team working within a limited timeframe while still enabling exploration of architectural trade-offs.

See the system architecture diagram in [System Architecture.md](System%20Architecture.md).

For the full intended product specification, see [Design Document.md](Design%20Document.md).

## Scope (In-Scope Functionality)

- Basic login/registration and a profile/portfolio view
- Creating item listings (title, price, description, and pictures)
- Viewing and browsing listings from other users
- Messaging the seller about a specific product (messages tied to that product)

## Access Control (YorkU Verification)

To limit access to valid York University members (students, faculty, professors), the system enforces registration using:

- `@my.yorku.ca` (students)
- `@yorku.ca` (faculty/staff)

## Architecture Risks and Mitigations

**Risks**

- **Time constraints:** delays in core features (e.g., authentication, messaging) can block the overall system.
- **Frontend–backend integration challenges:** API contract/data format mismatches can cause costly rework.
- **Uneven workload distribution:** central components can become bottlenecks or single-owner responsibilities.

**Mitigations**

- Divide development tasks evenly among team members.
- Break work into smaller tasks with weekly milestones.
- Review progress regularly to ensure deadlines are met and integrations stay aligned.

## Project Group

- Rajendra Brahmbhatt
- Michael Byalsky
- Daniel Chahine
- Lakshan Kandeepan
- Harnaindeep Kaur
- Mai Komar

## Status

This repository currently contains design/architecture documentation. Implementation details (setup, running the app, tests) can be added once the codebase is integrated into the repo.

