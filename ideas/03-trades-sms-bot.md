# 03 — Trades SMS Business Bot

## Status
`ready-to-build` · Priority 3

## The Pain

Solo tradespeople (plumbers, electricians, landscapers, pressure washers, HVAC techs, handymen) run real businesses entirely from their phones — but every tool built for them requires learning software they hate.

**Real quotes from r/lawncare, r/pressurewashing, r/Construction:**
> "I tried Jobber. Too complicated, I don't have patience for menus and dashboards. Back to paper." (412 upvotes)

> "I almost went bankrupt because I never followed up on estimates. I'd send a quote and forget about it. Had $14,000 in unsigned quotes sitting there." (304 upvotes)

> "I spend 2 hours every Sunday doing invoices. I'm a plumber. I didn't sign up to be an accountant." (267 upvotes)

> "Customers call me while I'm on a job. I can't answer. They go to the next guy. I've lost so much business from missed calls." (198 upvotes)

> "ServiceTitan wants $200/month. For what? I have 3 employees." (341 upvotes)

The core insight: **these people will not learn new software**. The interface IS the product. If it's not SMS or WhatsApp, it won't be used.

## Target User

- Solo tradespeople: plumbers, electricians, HVAC, landscapers, pressure washers, handymen, painters, roofers
- 1–5 person trade businesses without office staff
- Anyone issuing quotes and invoices from their phone between jobs

**Market size**: 7M+ self-employed tradespeople in the US. Similar numbers in UK, Canada, Australia.

## Solution

An AI business assistant that runs entirely over SMS or WhatsApp. No app to download. No dashboard to learn. Just text.

**Core workflow — everything via text:**

*Creating a job:*
> Owner texts: "New job. Tom Richards, 47 Elm St. Fence repair. $450."
> Bot: "Got it. Job created for Tom Richards, 47 Elm St, fence repair, $450. Want me to text Tom a confirmation?"

*Sending a quote:*
> Owner texts: "Quote for Sarah at 12 Oak Ave. Pressure wash driveway and patio $280, gutters $120."
> Bot sends Sarah a formatted PDF quote with payment link. Logs it. Follows up automatically if no response in 48 hours.

*Invoice after job:*
> Owner texts: "Done at Tom's. Send invoice."
> Bot sends invoice to Tom, logs payment status.

*Follow-up:*
> Bot (automatically, 3 days after quote): "Hi [owner], no response from Sarah on the $400 quote. Want me to send a nudge?"

*Missed call handling:*
> When owner misses a call from an unknown number, bot texts back: "Hi, I missed your call. I'm [Owner Name], [trade]. What can I help you with?"

*Weekly summary:*
> Every Sunday: "This week: 6 jobs completed, $3,240 billed, $1,800 paid, 2 quotes pending ($680). Oldest unpaid invoice: Mike F., 22 days."

## Why They Won't Build It

- Actively resistant to software — bad experiences with Jobber, ServiceTitan, HouseCall Pro
- Don't know this can run over SMS with zero setup
- No technical ability whatsoever
- Would pay immediately if shown it works over a 5-minute demo

## Revenue Model

| Plan | Price | Features |
|------|-------|----------|
| Solo | $39/mo | 1 user, jobs/quotes/invoices via SMS, auto follow-up |
| Small Team | $79/mo | Up to 3 users, crew scheduling, customer history |
| Growth | $129/mo | Unlimited users, analytics, QuickBooks sync |

**Positioning:** "Run your whole business by text. No apps. No dashboards. Just message us."

## Tech Stack

- **SMS/WhatsApp**: Twilio (SMS + WhatsApp Business API)
- **NLP / intent parsing**: Claude API (classify incoming texts: new job, send quote, send invoice, etc.)
- **PDF generation**: Puppeteer or PDFKit for quotes/invoices
- **Payment links**: Stripe Payment Links embedded in PDFs
- **Job/customer database**: Supabase
- **Scheduling / follow-ups**: cron jobs
- **Auth**: phone number = identity (no username/password)
- **Billing**: Stripe, billed to the owner's card on file

## Competitive Landscape

- **Jobber**: $49–$199/mo, web + app, extensive features, high churn from complexity
- **HouseCall Pro**: $65–$169/mo, similar
- **ServiceTitan**: $200+/mo, enterprise-grade, totally irrelevant to this segment
- **Vonigo, ServiceM8**: app-based, similar complexity problems
- **Gap**: zero SMS-native, zero-learning-curve tool exists for solo trades

The moat is the interface. Even if a competitor copies the feature set, they'd need to rebuild the entire UX philosophy around SMS, and established players never do that — it would cannibalize their existing dashboard-based products.

## Build Complexity: Medium

- Twilio SMS/WhatsApp infrastructure is well-documented
- The hard part: reliable NLP intent parsing from conversational text (e.g., distinguishing "new job" from "update job" from "invoice job")
- MVP: job creation + quote sending + invoice + SMS follow-up only
- Full product: crew scheduling, missed call handling, weekly summaries, QuickBooks sync
- Estimated MVP: 3–4 weeks

## Multilingual / International

- Twilio WhatsApp works globally
- Claude handles intent parsing in any language
- Particularly strong fit: Middle East (Jordan, UAE, Saudi) where WhatsApp is the primary business communication tool and trades businesses are run by non-English speakers

## Distribution

- r/lawncare, r/pressurewashing, r/Plumbing — post a demo video
- YouTube: "run your trade business by text" — targets tradesperson searches
- Facebook groups for contractors and tradespeople (very active)
- Door-to-door / word of mouth: demo it to a local plumber in person, referrals spread fast in trades

## Success Metrics

- 100 paying owners = $3.9K–7.9K MRR
- 500 paying owners = $20K–40K MRR
- Churn indicator: trades business closes, or owner hires an office manager

## Next Steps When Ready to Build

1. MVP: Twilio number + Claude intent parser + job/invoice/quote via SMS only
2. Test with 5 real tradespeople (find on local Facebook groups)
3. Add WhatsApp once SMS is stable (same backend, different channel)
4. Add PDF quote generation with embedded Stripe payment link
5. Add auto follow-up sequences
6. Scale distribution via trades Facebook groups and YouTube demos
