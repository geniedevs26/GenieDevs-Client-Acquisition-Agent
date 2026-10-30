# GenieDevs Client Acquisition Agent

A static lead CRM and Supabase-backed client order approval desk for GenieDevs.

## Deploy to Cloudflare Pages
1. Open Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git.
2. Select `geniedevs26/GenieDevs-Client-Acquisition-Agent`.
3. Framework preset: **None**.
4. Build command: leave blank.
5. Build output directory: `/` (repository root).
6. Deploy. The app is served from `index.html`.

## Features
- Separate `workflow.html` Order Approval Desk with Supabase authentication and shared order/approval records.
- Client order records created after client acceptance; stage-by-stage approval queue for financial proposal, agreement, project start, milestones, final delivery, and closure.
- Row-level security policies restrict order and approval records to the signed-in account owner.
- Lead records with country, public business contact, website, source URL, service opportunity, and a required business-specific observation.
- Search/filter pipeline and activity timeline.
- Drafts for initial email, follow-up, call opening, proposal outline, and agreement discussion draft.
- CSV import/export backups; duplicate check on non-empty email addresses.
- Opt-out and not-interested statuses block draft generation; opt-out is locked against accidental changes in the UI.
- Browser localStorage only; data stays in this browser profile unless exported.

## Current boundaries
The existing `index.html` remains a browser-local lead CRM. The new `workflow.html` stores order and approval records in Supabase. It records approval decisions but does not send proposals, agreements, milestone files, or final deliveries. Automatic lead discovery/verification, initial outreach, scheduled follow-ups, and PSTN/AI calls are not yet connected. These require a verified search/research integration, email sender, telephony provider, background scheduler, provider credentials, and legal-compliance controls. No private API credentials are committed to this repository.

## Privacy and security
Do not enter passwords, payment details, or sensitive personal information. Export CSV backups regularly. Clearing browser storage or using another browser/device may remove or hide records. Review drafts for accuracy before sending. The agreement output is a discussion draft, not legal advice.
