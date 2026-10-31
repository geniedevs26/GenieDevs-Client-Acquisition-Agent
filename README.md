# GenieDevs Client Acquisition Agent

A private-by-default lead CRM, AI Business Agent control panel, and Supabase-backed client order approval desk.

## Deploy to Cloudflare Pages
1. Open Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git.
2. Select `geniedevs26/GenieDevs-Client-Acquisition-Agent`.
3. Framework preset: **None**.
4. Build command: leave blank.
5. Build output directory: `/` (repository root).
6. Deploy. The main CRM is served from `index.html`; the AI Business Agent is `agent.html`.

## Current application areas
- `index.html`: browser-local lead CRM, lead pipeline, outreach draft builder, activity log and CSV import/export.
- `agent.html`: authenticated AI Business Agent control panel, daily target settings, prospect research request queue, integration readiness and outreach queue status.
- `workflow.html`: Supabase-authenticated client order and owner approval workflow for proposals, agreements, project start, milestones, final delivery and closure.
- Supabase Edge Function `agent-control`: authenticated status, safe settings and prospecting request endpoints.
- Supabase tables: leads, outreach actions, prospect search jobs, outreach queue, contact suppressions, client orders, approvals and audit history.

## Important live boundaries
The AI Business Agent control plane and database safeguards are deployed. This is **not yet a fully autonomous revenue-generating agent**. The following external execution integrations are not connected or verified:
- Automated lead discovery/search provider.
- Compliant email sender and inbound reply/bounce webhooks.
- PSTN telephony provider and AI voice runtime.
- Scheduled background worker to run discovery, send approved email, process replies and follow-ups.

The dashboard deliberately labels these integrations as not configured. Prospect search requests are recorded as `needs_review`, not falsely marked completed. No email or phone call is sent by the current Edge Function. Do not enable real outreach until the relevant provider, sender identity, consent/legal basis, suppression checks, webhook verification and spending controls are configured and tested.

## Safety and owner control
- No personal mobile/SIM calling.
- Automated marketing voice calls require recorded explicit consent.
- Owner approval remains required for outreach execution and all commercial decisions.
- Opt-outs and suppressed contacts must never be contacted again.
- Daily target is limited to 1–20 prospects; it is a target, not a promise of successful contacts.
- No paid service, trial credit or automatic upgrade is assumed.
- Never commit provider secrets to GitHub. Use provider-specific secret storage only after a legitimate zero-cost option is verified.

## Privacy and security
Supabase tables use row-level security scoped to the signed-in owner. The browser-only CRM stores its own leads in localStorage; export CSV backups regularly. Avoid storing passwords, payment details or sensitive personal information. Agreement drafts are for discussion and are not legal advice.
