# Tutorage

Tutorage is a location-based tutor discovery platform built for Karnataka.

Think of it as **“Zomato for Tutors”** — instead of discovering restaurants, students and parents discover nearby tutors on an interactive map.

The platform is focused primarily on individual home tutors who currently advertise through posters, gate signs, WhatsApp groups, and local word-of-mouth.

---

# Vision

Tutorage aims to digitize local tuition discovery by making tutors searchable, filterable, and discoverable in real-time.

Students can:
- Discover nearby tutors
- Filter tutors based on subject, class, board, and fees
- View tutor profiles
- Send inquiry requests
- Contact tutors directly

Tutors can:
- Create professional tutor profiles
- Pin their location on a map
- Receive student inquiries
- Build credibility with reviews and verification

---

# MVP Features

## Student Features

- Interactive map-based tutor discovery
- Search nearby tutors
- Subject-based filtering
- Class and board filtering
- Online vs physical tutor selection
- Tutor profile pages
- Inquiry request system
- Ratings and reviews

## Tutor Features

- Tutor registration portal
- Profile creation
- Subject and class selection
- Location pinning
- Upload profile photo
- Inquiry management
- Availability settings

## Admin Features

- Approve tutor registrations
- Remove spam accounts
- Manage tutor profiles
- View inquiries and analytics
- Verify tutor accounts

---

# Tutor Categories

Tutorage supports three tutor modes:

### 1. Home Tutor
Teacher teaches from their own home.

### 2. Traveling Tutor
Teacher travels to the student's home.

### 3. Online Tutor
Teacher teaches online via Zoom/Google Meet/etc.

Tutors can choose one or multiple modes.

---

# Tech Stack

## Frontend

- Next.js
- TypeScript
- Tailwind CSS
- Shadcn UI

## Backend

- Node.js
- NestJS

## Database

- PostgreSQL

## Authentication

- Firebase Authentication
- Google Login
- Phone OTP Login

## Maps & Location

- Mapbox

## Search

- Algolia

## File Storage

- Cloudinary

## Notifications

- Firebase Cloud Messaging

## Deployment

### Frontend
- Vercel

### Backend
- Railway

### Database
- Supabase

---

# Monorepo Structure

The project uses Turborepo.

```bash
apps/
   web/
   api/
   admin/
   mobile/ (future)

packages/
   shared/
   ui/
   database/
   config/
```

---

# Project Architecture

## Frontend

The frontend is built with Next.js and provides:

- Interactive tutor discovery
- Map UI
- Tutor profiles
- Authentication flows
- Responsive mobile-first experience

## Backend API

The backend API handles:

- Authentication
- Tutor management
- Inquiry system
- Reviews
- Notifications
- Admin operations

## Shared Packages

Shared packages contain:

- Shared TypeScript types
- Database schemas
- Reusable UI components
- Common utilities

---

# Core User Flow

## Student Flow

```text
Open app
↓
Choose:
[Physical Tutors]
[Online Tutors]
↓
Allow location access
↓
View nearby tutors on map
↓
Apply filters
↓
Open tutor profile
↓
Send inquiry
↓
Tutor receives notification
```

## Tutor Flow

```text
Register account
↓
Verify phone number
↓
Create tutor profile
↓
Select subjects/classes/boards
↓
Pin map location
↓
Publish profile
↓
Receive student inquiries
```

---

# Database Models

## Users

```ts
User {
  id
  name
  email
  phone
  role
}
```

## Tutor Profiles

```ts
TutorProfile {
  id
  userId
  subjects[]
  classes[]
  boards[]
  mode[]
  experience
  monthlyFee
  languages[]
  latitude
  longitude
  verified
  premium
}
```

## Inquiries

```ts
Inquiry {
  id
  studentId
  tutorId
  message
  status
}
```

## Reviews

```ts
Review {
  id
  rating
  comment
  tutorId
}
```

---

# Inquiry System

Students can send inquiry requests directly to tutors.

The platform does NOT process payments.

### Example Inquiry

```text
I need class 10 CBSE math tuition.
```

### Inquiry Statuses

- Pending
- Viewed
- Connected
- Expired

Inquiries automatically expire after 72 hours.

---

# Future Monetization

The MVP launches free for tutors.

The database is designed to support future monetization:

- Featured tutor listings
- Promoted profiles
- Subscription plans
- Premium badges
- Priority search ranking

---

# Design Goals

- Mobile-first
- Fast loading
- Minimal modern UI
- Google Maps + Zomato inspired UX
- Clean typography
- Interactive map-based browsing
- Responsive design

---

# Launch Strategy

Initial launch focus:

- Karnataka
- Localized tutor density
- Home tutors as primary supply source

### Suggested Rollout

1. Mangaluru
2. Bengaluru
3. Other Karnataka cities

---

# MVP Priorities

## Must Have

- Authentication
- Tutor registration
- Map integration
- Search & filtering
- Tutor profiles
- Inquiry system
- Admin dashboard
- Reviews

## Skip Initially

- AI recommendations
- In-app payments
- Real-time chat
- Advanced analytics
- Subscription billing

---

# Development Setup

## Install Dependencies

```bash
pnpm install
```

## Run Development Servers

```bash
pnpm dev
```

## Build Project

```bash
pnpm build
```

---

# Environment Variables

Example:

```env
DATABASE_URL=
NEXT_PUBLIC_MAPBOX_TOKEN=
FIREBASE_API_KEY=
FIREBASE_AUTH_DOMAIN=
ALGOLIA_APP_ID=
ALGOLIA_SEARCH_KEY=
CLOUDINARY_CLOUD_NAME=
```

---

# Long-Term Vision

Tutorage aims to become the default platform for discovering tutors across India.

Future roadmap:

- Mobile apps
- Subscription system
- Tutor verification pipeline
- Smart ranking system
- City-wide expansion
- Advanced analytics
- AI-assisted tutor matching

---

# License
all owned by manas gupta kesarla all rights reserved
MIT License
