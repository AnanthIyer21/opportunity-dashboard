# Daily update instructions (for the automated Claude task)

You are updating Ananth's opportunity dashboard. The single source of truth is
`opportunities.json` in this repo. The dashboard (`index.html`) renders it —
do not modify `index.html` unless it is broken.

## Profile (who this is for)

Mathematics & CS student. UK-based (UK work rights) with an Indian OCI card
(India work rights). Will travel to global hubs: London, SF/Bay Area, NYC,
Chicago, Zurich, Amsterdam, Berlin, Dublin, Toronto, Dubai, Bangalore/Mumbai,
Hong Kong, Singapore, Tokyo, Sydney. Interests: EVERYTHING relevant to a
math/CS student — quant trading/research, SWE, AI/ML, research fellowships,
startups/deeptech, hackathons, competitions (trading, data science, ML, math),
founder programs, tech events/conferences.

## Each morning, do exactly this

1. Read `opportunities.json`. Note today's date.
2. PRUNE: remove entries whose dated deadline passed more than 7 days ago, and
   events whose end date has passed. Keep recently-closed (≤7 days) items so
   the dashboard shows what was missed.
3. REFRESH: for 5–8 existing "TBA" or "Rolling" entries (rotate through them),
   check whether deadlines/dates have been announced and update the entry.
4. DISCOVER: search the web for NEW opportunities not already in the file.
   Aim for 3–8 genuinely good new items a day, quality over quantity. Rotate
   focus across the week so everything gets covered:
   - Mon: quant internships/comps + trading firm programs
   - Tue: SWE/AI-ML internships, new-grad roles, residencies/fellowships
   - Wed: hackathons (ETHGlobal, MLH, university, AI-lab hackathons)
   - Thu: startup/founder programs, grants, accelerators
   - Fri: competitions (Kaggle, math/CS, datathons, case comps) + research programs
   - Sat: events/conferences + India-specific opportunities (OCI angle)
   - Sun: sweep of "closing soon" lists + anything missed this week
5. VERIFY every new item before adding: fetch the URL, confirm it loads, is
   currently open (or opening within ~2 months), and the deadline is real.
   Never add an item you could not verify. Use official pages as `url`.
6. Update the JSON:
   - Set top-level `"updated"` to today's date (YYYY-MM-DD).
   - New items get `"added"` = today. NEVER change `added` on existing items.
   - Keep ids kebab-case and unique. Do not duplicate an existing opportunity
     (check by org + title similarity, not just id).
   - Schema per item: id, title, org, type (internship|job|competition|
     hackathon|event|program|fellowship), category (quant|swe|ai-ml|research|
     hackathon|startup|deeptech|other), location, region (UK|Europe|US|Canada|
     India|APAC|MENA|Global), deadline (YYYY-MM-DD|Rolling|TBA), dates,
     pay_or_prize, url, eligibility, notes, added.
7. Validate the JSON parses (e.g. `python3 -c "import json;json.load(open('opportunities.json'))"`).
8. Commit and push to `main` with message `daily update YYYY-MM-DD (+N new, -M removed)`.
9. If any newly found item closes within 72 hours, mention it prominently in
   your completion summary so the push notification is useful.
