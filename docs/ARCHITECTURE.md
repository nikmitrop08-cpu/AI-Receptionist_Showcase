# Architecture and data flow

## Components

1. **Vite web frontend** manages authenticated business interactions and voice-session UI.
2. **FastAPI** exposes authenticated business, scheduling, customer, AI, lead and call routes.
3. **Supabase Auth** validates bearer tokens via the `/auth/v1/user` endpoint; the API maps the identity to `UserProfile` and its business.
4. **SQLAlchemy database layer** stores business settings, services, hours, appointments, customers, calls and leads.
5. **AI orchestration** uses a conversational model and explicit tools to perform availability checks, bookings and lead creation.
6. **Audio services** use `gpt-4o-mini-transcribe` and `gpt-4o-mini-tts` in the inspected source.

## Booking flow

A user starts a session; the API checks the business AI-enabled setting and creates a conversation and call record. Voice input is transcribed, interpreted by the conversational service, and may trigger `check_availability` or `book_appointment`. The booking implementation uses a PostgreSQL advisory transaction lock and rechecks availability before inserting an appointment. A response is generated for the customer, and the session can be finalized.

## Scheduling rules

Slots use 30-minute start increments, account for service duration, apply date-specific hours overrides, exclude cancelled appointments from occupancy, and avoid returning elapsed slots for the current day. The inspected code uses the `Europe/Athens` timezone.


