# GenieDevs Client Acquisition Agent

A private-by-default business command center backed by Supabase.

## Live site
Cloudflare Pages: https://geniedevs-client-acquisition-agent.pages.dev/

## Pages
- `index.html`: primary Business Command Center — authenticated live metrics, client-confirmed leads, separate research candidates, outreach records, orders, finance and activity history.
- `agent.html`: detailed AI Business Agent console and on-demand worldwide prospect research.
- `workflow.html`: client order and owner approval workflow.

## Current working capabilities
- Supabase authentication and owner-scoped data access.
- Worldwide on-demand public-source discovery using Hacker News Algolia and GitHub Issues.
- Candidate deduplication and storage in `leads` with `lead_status = needs_review`; candidates are not counted as confirmed leads.
- Separate client-confirmed lead view based on `client_confirmed_at`.
- Outreach queue and action history visibility.
- Client order and approval tracking.
- Income, expense, refund and net recorded finance metrics.
- Automation event history and daily research target settings.
- Contact suppression records and owner approval safeguards.

## Not yet operational — do not represent as automated
- Scheduled background prospect discovery.
- Automated email delivery.
- Incoming email reply and bounce webhooks.
- Automated phone calls / AI voice.
- Automatic follow-up execution.

These integrations require a configured scheduler, compliant provider credentials, verified sender identity/webhooks, and explicit legal/consent controls. The current Edge Function performs on-demand research only. It does not send email or make calls. A search candidate is not a qualified paid lead: verify the active request, requester, budget and a practical contact route before qualification.

## Safety
- Owner authentication and row-level security are required.
- No personal SIM/mobile calling.
- Automated marketing voice calls remain disabled unless recorded explicit consent and applicable legal controls are in place.
- Owner approval is required before external outreach and commercial actions.
- Honour opt-outs and contact suppression records.
- Never commit provider secrets to GitHub.
- Do not enable paid services or automatic spending without explicit approval.
