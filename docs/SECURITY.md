# Security posture and known limitations

## Observed controls

- Supabase access tokens are checked server-side against the Supabase user endpoint.
- A local user profile resolves to a business, and reviewed business operations use business IDs to scope queries.
- OpenAI API credentials are read on the backend rather than returned to the browser.
- The API has a localhost-only CORS origin in the inspected configuration.
- The booking tool uses a PostgreSQL advisory transaction lock and a fresh availability check to reduce booking races.

## Not independently verified

No penetration test, deployment review, secrets scan, load test, production monitoring evidence, or complete authorization test suite was provided. Do **not** advertise the system as penetration-tested, fully tenant-isolated, GDPR-compliant, highly available or production-ready.

## Recommended next work

1. Audit every route for business-level authorization, including direct object lookups and updates.
2. Add negative cross-business API tests and booking-concurrency tests.
3. Add database migrations instead of `Base.metadata.create_all()` at startup.
4. Add rate limits, request-size limits, audio retention policy, redaction and logging controls.
5. Review customer-consent, recording disclosure, deletion and privacy obligations before real-world usage.
6. Verify model availability/configuration and benchmark voice latency with reproducible measurements.
7. Keep `.env`, credentials, databases and personal data out of Git and public screenshots.
