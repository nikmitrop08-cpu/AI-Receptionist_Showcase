# AI Receptionist — Portfolio case study

**Role:** Independent software developer  
**Stage:** Working prototype / active development  
**Focus:** Python backend, AI tool integration, scheduling logic, authentication

## Problem

Businesses must answer repetitive service and appointment questions while keeping availability and bookings consistent with operating hours and existing reservations.

## Solution

I built an AI receptionist prototype that connects a voice conversation to a FastAPI business backend. Instead of only producing conversational text, the assistant can invoke structured operations to check availability, book appointments and record prospective leads.

## Engineering highlights

**Actionable AI:** Explicit function/tool definitions connect conversational intent to validated business operations.

**Scheduling constraints:** The slot engine handles service duration, operating hours, overrides, existing bookings and past slots.

**Identity and tenancy:** Supabase-authenticated users map to business profiles; backend operations are scoped to business records. Comprehensive isolation testing remains a planned verification step.

**Booking integrity:** The reviewed booking implementation uses a transaction-level PostgreSQL advisory lock and availability recheck before insertion.

## Evidence

Architecture diagram, voice-booking sequence diagram, and a supplied 8-minute platform walkthrough, plus cropped screenshots of the calendar, AI configuration, call history and customers. A call outcome displays `booking_completed` and the calendar contains the corresponding example appointment. No performance measurements are claimed.

## Next steps

Automated integration tests, tenant-boundary regression tests, migrations, latency measurements, improved frontend UX and privacy/retention policies.
