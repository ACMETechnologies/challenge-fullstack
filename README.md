# Full-Stack Take-Home Challenge (Angular + Spring Boot)

At Peek, we build software for tour and activity operators to run their businesses. One essential feature is the back-office calendar where operators can schedule events, view orders, and see how many guests are arriving on any given day.

For this challenge, we're using **Angular** for the frontend and **Java/Spring Boot/Hibernate/PostgreSQL** for the backend.

## Expected Time & Effort

We don't want you to take too much time with this challenge. Please **do not spend more than 4 hours**.

**Important:** We know you have access to AI tools (Copilot, ChatGPT, Claude, etc.). **You are encouraged to use them.** We want to see how effectively you use AI as a tool, and your ability to understand, validate, and improve AI-generated code.

---

## The Sample Project

### Server (Java/Spring Boot)

The `server-java` folder contains:
- **Event** and **Booking** JPA entities defined
- **EventRepository** and **BookingRepository** with JPA queries
- **EventService** and **BookingService** with business logic
- **EventController** with GET endpoints for listing events
- A `BookingService.createBooking()` method already implemented
- A data seeder that populates sample events (run with `seed` profile)
- Unit tests demonstrating service testing

### Client (Angular)

The `client-angular` folder contains:
- An Angular 17+ standalone component architecture
- **EventService** with HTTP calls to the REST API
- A **CalendarComponent** that displays events in a day view
- Basic routing and styling

---

## Problem Description

### Required Tasks

1. **Display events in a Google Calendar-style day view** (partially implemented - review and improve)

2. **Add the ability to create a booking for an event:**
   - Create a POST endpoint in `BookingController` that uses `BookingService.createBooking()`
   - Create a booking form/dialog in Angular that appears when clicking an event
   - Wire up the form to call the new API endpoint

### Extras (if time permits)

- Filters when retrieving events (by date range, title search)
- UI for viewing multiple days (week view)
- Display booking count on each event
- Validation and error handling
- Any improvements to existing code
- Unit tests for your new code

---

## AI Usage Questions (Required)

**Please answer these questions in a `AI_USAGE.md` file in your submission:**

1. **Which AI tools did you use during this challenge?** (e.g., GitHub Copilot, ChatGPT, Claude, Cursor, etc.)

2. **Describe a specific instance where AI helped you solve a problem.** What was the problem, what did the AI suggest, and did you use the suggestion as-is or modify it?

3. **Describe any AI-generated code you had to modify or reject.** How did you identify the issue? If everything worked correctly, what did you double-check anyway?

4. **For the booking feature, describe your approach:**
   - Did you ask AI to generate the entire feature, or did you break it into smaller prompts?
   - How did you validate that the generated code was correct?

5. **What's one thing you would NOT trust AI to do correctly without careful review?**

---

## Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | Angular 17+, TypeScript, RxJS, SCSS |
| Backend | Java 21, Spring Boot 3.2, Spring Data JPA, Lombok |
| Database | PostgreSQL 16 |
| Build Tools | Maven, npm/yarn |
| Containerization | Docker, Docker Compose |

---

## Setup Instructions

### Server Setup

**With Docker (recommended):**

```sh
cd server-java
docker-compose up --build
```

This starts PostgreSQL and the Spring Boot app with sample data.

**Local Development:**

Requirements: Java 21, Maven, PostgreSQL

```sh
cd server-java

# Start PostgreSQL locally or use Docker for DB only:
docker-compose up db

# Run the application with seed data:
mvn spring-boot:run -Dspring-boot.run.profiles=seed

# Or without seeding:
mvn spring-boot:run
```

The API is available at: `http://localhost:8080/api/events`

**Running Tests:**

```sh
mvn test
```

### Client Setup

Requirements: Node.js 18+, npm or yarn

```sh
cd client-angular
npm install
npm start
```

Visit: `http://localhost:4200`

---

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/events` | List all events |
| GET | `/api/events/{id}` | Get event by ID |
| GET | `/api/events/date/{date}` | Get events for a specific date (YYYY-MM-DD) |
| GET | `/api/bookings/event/{eventId}` | Get bookings for an event |
| POST | `/api/bookings` | Create a booking (TODO: implement) |

---

## Submission

1. Create a private GitHub repo and share access with `PeekTechTask`
2. Include your `AI_USAGE.md` file with answers to the AI questions
3. Make logical commits so we can follow your progress
4. Optionally include notes about your approach or any trade-offs made

---

## Learn More

- [Angular Documentation](https://angular.dev/)
- [Spring Boot Documentation](https://docs.spring.io/spring-boot/docs/current/reference/html/)
- [Spring Data JPA](https://docs.spring.io/spring-data/jpa/docs/current/reference/html/)
- [PostgreSQL](https://www.postgresql.org/docs/)

---

## Questions?

If you have any questions, please reach out to us at [martin@peek.com](mailto:martin@peek.com)

