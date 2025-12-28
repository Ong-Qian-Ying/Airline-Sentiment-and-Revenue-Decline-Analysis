# Airline-Sentiment-Revenue-Decline-Analysis
## Executive Summary:
SkyWings Airlines is facing a sharp revenue decline (Business −26%, Economy −18% YoY) alongside a deteriorating online brand image and average customer rating of 3/5. Using provided bookings and review datasets (2023-2024), my team and I built a KNIME text-mining workflow and two interactive Tableau dashboards + a management story connect customer feedback with booking performance and identify the highest-impact levers for recovery. Findings suggest declining trust driven by reliability and service shortcomings, with the largest upside in retaining and winning back returning Economy flyers. Hence, we recommended SkyWings to:

1. Reduce cancellations and strengthen service recovery with a 3-stage “Service Netting” plan (prevent, respond, recover).
2. Win back returning Economy customers using loyalty-style benefits and targeted outreach.
3. Redesign promotions to be more visible and targeted, then track uplift over time.

## Business Problem:
For an airline, bookings and reputation directly drive revenue. SkyWings, once popular for competitive pricing, is now seeing declining bookings and rising negative reviews. With customer reviews and transaction data available, SkyWings needs an analytical workflow to understand "What is causing the decline in business performance and what changes should be prioritised to reverse it?"

## Methodology:

1. KNIME text cleaning & document prep to convert Cust_Reviews into analysable text (Excel/CSV import → Strings to Document → de-dup → remove punctuation/numbers/stop words → lowercase + stemming).
2. KNIME sentiment + keyword extraction using MPQA lexicons (Dictionary Tagger → Bag of Words + Term Frequency → convert tags/terms to strings → filter missing → group/sum term frequencies → split positive vs negative → Tag Cloud) and export the cleaned sentiment-keyword output to Excel.
3. Tableau dashboard + story combining Fact_Trans, Cust_Reviews, and the KNIME export to visualise (a) positive/negative word clouds + (b) transaction KPI charts, add interactivity, and translate insights into retention + service-recovery recommendations.

## Skills:
**KNIME**: Lexicon-based sentiment text mining (pre-processing, MPQA enrichment, bag-of-words + term frequency keyword extraction)

**Tableau**: Multi-source data setup, calculated fields, interactive dashboards + story (KPI trends, segmentation, filters/tooltips)

**Analytics**: Customer sentiment analysis, KPI diagnostics + benchmarking, insight-to-recommendation storytelling

## Results & Business Recommendation:
### Key results & implications:
- Revenue fell >19% YoY (2024 vs 2023) because bookings fell, especially among repeat flyers.
  - **Implication**: The priority is retention/ win-back, not just acquisition.
- While Business class revenue fell more than Economy (25% vs 18% YoY), the biggest volume decline is in returning Economy bookings, and returning Economy customers generate more total revenue than new Economy through frequent repeat trips.
  - **Implication**: Returning Economy customers is the highest-ROI segment to fix.
- Cancelled flight rates are significantly higher than industry norms (15% vs 2% in 2024). 
  - **Implication**: Cancellations are the main operational "trust breaker" driving lost bookings and negative sentiment.
- Sentiment is net-negative (37% negative vs 30% positive). Complaints cluster around customer service (35.08%) and low quality perception (34.6%). Although physical quality complaints like seat discomfort exist, they are relatively minor (9.5%), and “comfort” appears frequently in positive reviews.
  - **Implication**: Given that disatisfaction is driven more by "intangibles" than product features, improving service experience + perceived value is critical to rebuild trust and repeat bookings.
- Promo codes are underused (16.91% of bookings) despite SkyWings' positioning around competitive pricing.
  - **Implication**: Promotions may lack visibility/ targeting and aren't currently supporting retention and its price-led value. 

### Business recommendations (prioritised)
1. **Reduce cancellations and strengthen disruption handling (“service netting”)**
   - Prevent avoidable disruptions, communicate early, and offer immediate rebooking/compensation to minimise trust erosion.
2. **Win back returning Economy customers (highest-value repeat segment)**
   - Launch loyalty perks (e.g., priority boarding/seat selection) and proactively target lapsed returning customers with recovery offers/service guarantees.
3. **Redesign promotions to be targeted “win-back” campaigns (not generic discounts)**
   - Shift to personalised, time-triggered offers (birthday/anniversary/welcome-back) and test referral-style incentives to drive repeat bookings.
  
## Next Steps (to address limitations of this project):
1. **Strengthen the data so insights can be tied to action.**
   - Augment the provided 2023–2024 extracts with operational CX metrics (support response time/FCR, refund turnaround, rebooking success) and additional VoC sources (tickets/chats/surveys), and where possible link feedback to flight outcomes + segments to quantify impact on repeat bookings and revenue.
2. **Move from theme counts to theme severity + drivers.**
   - Weight themes by rating/strong negative language to identify “high-severity” issues, and split themes by disruption type (cancellation vs delay) to pinpoint the most damaging journey moments.
3. **Quantify ROI and run controlled tests on the fixes.**
   - Pilot the service netting recovery plan and targeted win-back promos (with A/B-tested urgency formats), tracking lift in repeat bookings, cancellation-related complaints, and promo redemption.
4. **Operationalize a “VoC → KPI” monitoring loop.**
   - Turn this into a recurring dashboard that flags spikes in cancellations/negative themes early, so leaders can intervene before booking decline worsens.
