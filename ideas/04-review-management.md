# 04 — Google Review Management + Auto-Requests

## Status
`ready-to-build` · Priority 4

## The Pain

Reviews are the lifeblood of any consumer-facing local business — restaurants, salons, clinics, trades, retail — yet most small business owners are either ignoring them, responding inconsistently, or paying agencies $500–2K/month for something AI can do.

**Real signals from forums:**
- A Reddit post asking "What's the best site to buy fake Google reviews?" hit **10,000 upvotes** — capturing the desperation of small business owners who feel powerless about reviews
- r/smallbusiness has hundreds of threads on review anxiety, not knowing how to respond, and competitors gaming the system

**Real quotes:**
> "A competitor left us 6 fake 1-star reviews. We reported them, Google did nothing. We went from 4.8 to 4.1 overnight. Sales dropped 30%." (892 upvotes)

> "I have no idea how to respond to a bad review without sounding defensive. Every time I try it comes out wrong." (567 upvotes)

> "We have 200 happy customers who've never left a review. Every time I ask them in person they say they will and then don't." (445 upvotes)

> "Our agency charges $800/month to monitor and respond to reviews. I'm a 3-person restaurant. That's insane." (334 upvotes)

Two distinct pain points bundled in one tool: (1) responding to reviews that exist, and (2) generating new reviews from happy customers.

## Target User

- Restaurants, cafes, food trucks
- Salons, spas, barbershops
- Dental and medical clinics
- Auto repair shops
- Any consumer-facing local business with Google Business Profile

**Market size**: 33M+ small businesses in the US have a Google Business Profile. Internationally, similar density in UK, Canada, Australia, Middle East.

## Solution

Two-function tool with one dashboard:

**Function 1 — Review Response AI:**
1. Connects to Google Business Profile via API
2. Monitors for new reviews (1–5 stars)
3. Drafts a personalized response in the owner's voice within minutes
4. Sends response draft via SMS/WhatsApp for one-tap approval
5. Auto-responds to common patterns (if owner enables it) — e.g., all 5-star reviews get an immediate thank-you

**Function 2 — Review Request Automation:**
1. Owner texts/inputs a customer's name and phone after a completed job/visit
2. System sends a personalized SMS: "Hi [Name], it was great having you in today! If you have 30 seconds, we'd love a review — it helps our small business a lot. [link]"
3. Timing optimization: sends when response rates are highest (research shows 1–4 hours after visit)
4. Handles opt-outs automatically
5. Tracks which customers were asked, who responded, conversion rate

**Bonus — Negative Review Early Warning:**
- If sentiment from any channel (Google, Yelp, Facebook) drops, owner gets an immediate SMS alert before a bad review goes live — allows proactive customer recovery

## Why They Won't Build It

- Google Business Profile API requires OAuth setup — non-technical owners can't do it
- Don't know AI can draft responses that sound like them
- Have never heard of review request automation
- Current "solution" is either ignoring reviews or paying an agency

## Revenue Model

| Plan | Price | Features |
|------|-------|----------|
| Starter | $49/mo | 1 location, review monitoring + AI responses, 100 review requests/mo |
| Growth | $99/mo | 3 locations, unlimited review requests, auto-response mode, analytics |
| Multi-Location | $199/mo | Up to 10 locations, white-label reports, priority support |

**Positioning:** "Respond to every review in your voice. Generate 5x more reviews. Takes 2 minutes to set up."

## Tech Stack

- **Google Business Profile API**: for review monitoring and posting responses
- **Yelp API + Facebook Graph API**: for multi-platform monitoring (Growth plan)
- **SMS**: Twilio for review requests and owner approvals
- **AI drafting**: Claude API (system prompt with owner's voice samples from previous responses)
- **Auth**: Google OAuth for GBP connection
- **Billing**: Stripe

## Competitive Landscape

- **Birdeye**: $299–$499/mo, enterprise-heavy, way over-priced for small biz
- **Podium**: $289–$449/mo, same issue
- **NiceJob**: $75/mo, review request focused, no AI response drafting
- **Grade.us**: $110+/mo, agency-focused
- **Gap**: affordable ($49–99/mo), AI-native, SMS-approval-based tool for individual small business owners

This is the most competitive of the 4 ideas — but it's competitive because the market is validated and massive. Winning on price + simplicity is viable.

## Build Complexity: Medium

- Google Business Profile API is well-documented but OAuth setup adds friction
- Multi-platform support (Yelp, Facebook) adds complexity — defer to v2
- MVP: Google only + SMS approval + review requests
- Estimated MVP: 3–4 weeks

## Distribution

- r/smallbusiness, r/restaurantowners, r/Entrepreneur
- Local business Facebook groups
- Direct outreach to restaurants/salons in target cities
- SEO: "how to respond to google reviews", "get more google reviews small business"
- Partnerships with point-of-sale providers (Square, Toast) as an add-on

## Success Metrics

- 100 paying businesses = $4.9K–9.9K MRR
- 500 paying businesses = $25K–50K MRR
- Churn indicator: business closes, or switches to agency

## Next Steps When Ready to Build

1. MVP: Google Business Profile OAuth + review monitoring + AI draft + SMS approval
2. Add review request automation (Twilio → customer SMS → tracking)
3. Validate pricing with 10 beta users (offer free for 60 days, get testimonials)
4. Launch on ProductHunt and local business forums
5. Add Yelp + Facebook monitoring in v2
