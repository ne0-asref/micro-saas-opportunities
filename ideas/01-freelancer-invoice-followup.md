# 01 — Freelancer Invoice Follow-Up Agent

## Status
`ready-to-build` · Priority 1

## The Pain

54% of freelancers experience delayed payment at least once per quarter. 59% are owed $50K+ in outstanding invoices at any given time. The problem isn't just financial — it's emotional. Writing "just checking in on this invoice" for the fifth time is one of the most consistently-cited frustrations in freelancer communities.

**Real quotes from r/freelance:**
> "I have a client who is 90 days overdue. Every time I email them I feel sick. I don't know whether to be professional or firm and I always end up sounding desperate." (312 upvotes)

> "I spent 3 hours this week writing follow-up emails for unpaid invoices. That's time I could have been working or pitching." (198 upvotes)

> "I once wrote 14 follow-up emails to the same client over 4 months. I finally got paid. I also lost a year of my life." (276 upvotes)

The pattern across hundreds of posts: freelancers know what needs to happen, they just hate doing it, feel anxious about tone, and keep putting it off — which makes the situation worse.

## Target User

- Freelancers: designers, copywriters, consultants, photographers, video editors, developers (non-technical segment)
- Independent contractors: marketing consultants, social media managers, bookkeepers
- Anyone issuing invoices without a finance team behind them

## Solution

An AI agent that monitors unpaid invoices and handles the entire follow-up sequence automatically, in the freelancer's tone and voice.

**Core workflow:**
1. Freelancer connects their invoicing tool (FreshBooks, Wave, QuickBooks, or manual upload)
2. Agent monitors invoice statuses
3. When an invoice goes unpaid past the due date, the agent kicks off an escalating sequence:
   - Day 1 past due: friendly reminder ("Hey, just wanted to make sure this landed in the right inbox")
   - Day 7: gentle nudge with payment link
   - Day 14: firmer note referencing the original agreement
   - Day 30: formal notice with late fee language if applicable
4. All emails sent for one-tap approval via SMS, or auto-sent if the user enables it
5. Flags chronic late-payers and suggests adding upfront deposits for future work with them
6. Weekly digest: what's been sent, what's outstanding, what was recovered

**Tone customization:** user pastes 3 sample emails they've written before; agent matches their voice.

## Why They Won't Build It

- Not technical — can't set up automations
- Don't know AI could draft and send emails on their behalf
- Would use a tool if it existed and was simple enough to set up in 5 minutes

## Revenue Model

| Plan | Price | Features |
|------|-------|----------|
| Solo | $19/mo | Up to 20 active invoices, email only |
| Pro | $39/mo | Unlimited invoices, SMS approval, tone matching, late fee templates |
| Studio | $79/mo | Up to 5 team members, analytics, CRM notes per client |

**Positioning:** "Recover what you're owed without the awkward emails."

## Tech Stack

- **Invoice integrations**: FreshBooks API, Wave API, QuickBooks Online API — or simple CSV/manual entry as fallback
- **Email sending**: SendGrid or Postmark
- **SMS approvals**: Twilio
- **AI drafting**: Claude API (system prompt with user's tone samples)
- **Scheduling**: cron jobs per invoice
- **Auth + billing**: Clerk + Stripe

## Competitive Landscape

- **HoneyBook / Dubsado**: full CRM suites, $16–$20/mo, not focused on follow-up, too heavy for many freelancers
- **Nudge** (now defunct): tried this exact model, product disappeared — market gap confirmed
- **Manual Gmail filters + Zapier**: some power users do this but it's fragile and still requires writing the emails

No direct, simple, AI-native competitor exists at this price point.

## Build Complexity: Low

- Standard API integrations
- Email/SMS infrastructure is commodity
- AI drafting is a single well-tuned system prompt
- MVP possible in 1–2 weeks

## Distribution

- r/freelance, r/graphic_design, r/copywriting communities
- Freelancer-focused newsletters (Freelance Isn't Free, etc.)
- ProductHunt launch
- SEO: "freelancer invoice follow up template", "how to ask client for payment email"

## Success Metrics

- 100 paying users = $2K–4K MRR
- 500 paying users = $10K–20K MRR
- Churn indicator: integration breaks or freelancer goes full-time employee

## Next Steps When Ready to Build

1. Define MVP scope: email-only, manual invoice entry, 3-step sequence
2. Pick one invoicing integration to start (Wave is free and has API)
3. Build tone-matching prompt with 5–10 sample freelancer email styles
4. Set up Stripe billing + simple onboarding (invoice connect → sequence config → go)
5. Soft launch to r/freelance with a free 30-day trial
