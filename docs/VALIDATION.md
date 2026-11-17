# Employer-facing verification checklist

Mark an item PASS only after running it and saving evidence. Source review alone is not an execution test.

- [ ] Authenticated user can access their business configuration
- [ ] Unauthenticated request is rejected
- [ ] Business A cannot access Business B data
- [ ] AI-off business cannot create a voice session
- [ ] Voice transcription returns intelligible text
- [ ] Availability respects closed days, overrides, service duration and existing appointments
- [ ] Booking creates exactly one appointment at the confirmed time
- [ ] Repeated/concurrent booking attempts do not double-book
- [ ] Call finalization produces the expected call record
- [ ] Lead capture stores a lead when no appointment is booked
- [ ] No API keys, access tokens, customer phone numbers or private records appear in evidence
- [ ] Backend tests run and results are captured with date/commit

## Review status

**Source inspection completed; live functional and automated test results not supplied.** The uploaded `backend/tests` folder includes `test_businesses.py` and helper scripts, but no comprehensive verification report was supplied.
