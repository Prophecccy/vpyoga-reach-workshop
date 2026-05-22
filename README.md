# VP YOGA - REACH: THE BEST VERSION OF YOU

Crafted by Specturn.

## Overview
This repository contains the official workshop website and registration system for **REACH – The Best Version of You**.

It includes:
- A public landing page with workshop details
- Google-authenticated participant registration
- Payment submission via UPI transaction reference
- Participant status check and ticket download flow
- Ticket verification page for authenticity checks
- Admin panel for reviewing registrations and confirming payments

## Tech Stack
- **Frontend:** React 18 + TypeScript + Vite
- **Styling:** Tailwind CSS
- **Routing:** React Router
- **Backend services:** Firebase Authentication + Firebase Realtime Database
- **Forms:** Formspree
- **PDF/Ticket generation:** jsPDF + QRCode
- **Maps:** Leaflet + React Leaflet

## App Routes
- `/` and `/reach-workshop` – Main workshop page
- `/submission-received` – Confirmation screen after submission
- `/check-status` – Participant registration/payment status checker
- `/verify-ticket/:verificationCode` – Ticket verification view
- `/admin` – Admin login and registration management panel

## Key Functional Flows
### Participant registration
1. Sign in with Google
2. Pay workshop fee via UPI QR
3. Enter profile + transaction details
4. Submit registration

### Status and ticket
- Participants can check payment status with their authenticated email.
- Once payment is marked confirmed by admin, they can download their workshop ticket.

### Admin operations
- Admin signs in via Firebase auth.
- Admin can view all registrations and toggle `paymentConfirmed` status.

## Environment Variables
Create a `.env` file in the project root and provide:

```env
VITE_FIREBASE_API_KEY=
VITE_FIREBASE_AUTH_DOMAIN=
VITE_FIREBASE_PROJECT_ID=
VITE_FIREBASE_STORAGE_BUCKET=
VITE_FIREBASE_MESSAGING_SENDER_ID=
VITE_FIREBASE_APP_ID=
VITE_FIREBASE_MEASUREMENT_ID=
VITE_FORMSPREE_REGISTRATION_ID=
```

## Local Development
### Prerequisites
- Node.js (LTS recommended)
- npm

### Install
```bash
npm ci
```

### Run locally
```bash
npm run dev
```

### Build for production
```bash
npm run build
```

### Lint
```bash
npm run lint
```

## Project Structure
```text
src/
  components/      # Workshop page sections and shared UI
  pages/           # Route-level pages (admin, status, verification, etc.)
  contexts/        # Auth context/provider
  config/          # Firebase initialization
  utils/           # Utility helpers (ticket/pdf generation)
  types/           # Shared TypeScript types
```

## Notes
- Firebase Realtime Database path used for registrations: `registrations`
- Registration and status flows are tied to authenticated user email

