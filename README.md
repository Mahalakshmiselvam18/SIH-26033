# Smart India Hackathon Workshop
# Date: 25/11/2026
## Reference Number :26008631
## Name: Mahalakshmi S

## Problem Title
SIH 26033: Multiple intermediaries reduce farmers earnings and increase consumer prices.

## Problem Creater's Organization
Ministry of Consumer Affairs, Food & Public Distribution

## Theme
Agriculture, FoodTech & Rural Development

## Problem Description
Expected Solution: Create a digital marketplace that:

• Connects farmers/FPOs directly with consumers and bulk buyers.
• Provides logistics support.
• Uses AI for demand forecasting and route optimization.

Benefits:

• Better prices for farmers.
• Lower prices for consumers.
• Reduced supply chain inefficiencies.

## Proposed Solution

**Idea:** Farmers, retailers, bulk buyers and consumers all earn more when they trade on ONE common platform instead of through many middlemen. We propose a mobile app and website where farmers/FPOs list their expected stock, and buyers pre-book it up to a week or more in advance. AI matches each order with the best farmer, and the platform arranges delivery.

**How it works**

1. **Farmer/FPO lists stock:** crop, quantity, expected harvest date, location and the price they demand.
2. **Buyer posts a requirement:** a bulk buyer, retailer or hotel books the quantity needed for a date about a week ahead. Individual consumers can order small quantities.
3. **AI matching:** the system finds the best farmer(s) by crop, quantity, distance, quality rating and price. It can combine several farmers or FPOs to fill one large order.
4. **Price acceptance:** the buyer sees the farmer's demanded price along with the AI's fair price range. If the buyer accepts, the order is confirmed automatically. If not, the AI suggests the next best match.
5. **Secure payment:** the buyer's payment is held in escrow (UPI) and released to the farmer after delivery is confirmed.
6. **Logistics support:**
   - Bulk loads: truck/mini-truck booking through the app, with load pooling.
   - Small and home deliveries: bike/auto partners (a Rapido-like service) for last-mile delivery.
   - Buyers can choose **self-pickup** or **home delivery**.
7. **Unsold-stock safety net:** if stock is not sold before harvest or the shelf-life limit, the app automatically routes it to the **nearest market committee (APMC/mandi)** with a transport booking. The platform also shows the expected mandi price so the farmer does not lose the harvest or sell at a loss.

**What is new here**
- Pre-booking makes demand certain before harvest, so farmers plan better.
- Automatic farmer-buyer matching and price negotiation, with no broker.
- A built-in fallback to mandi, which protects the farmer from total loss.
- Delivery, payment and quality checks sit inside one app.

## Technical Approach
"C:\Users\acer\OneDrive\Pictures\Screenshot (19)max.png"
"C:\Users\acer\OneDrive\Pictures\Screenshot (18).max.png"

**Users and modules**
- Farmer/FPO app: stock listing, price setting, order tracking, wallet.
- Buyer app: search, pre-booking, price acceptance, delivery choice, tracking.
- Admin/mandi dashboard: monitoring, disputes, mandi stock intake.
- Delivery partner app: pickup and drop tasks.

**AI/ML components**
- **Demand forecasting:** time-series models (e.g., Prophet/LSTM) trained on past orders, season, festivals and mandi price data. This tells farmers what to grow and sell.
- **Price recommendation:** a regression model suggesting a fair range from mandi prices, demand and quality.
- **Matching engine:** a scoring and optimization algorithm (distance, quantity, price, rating, freshness) to pair farmers and buyers and to split large orders across farmers.
- **Route optimization:** vehicle routing algorithms (Google OR-Tools / Maps API) for load pooling, plus nearest-mandi selection for unsold stock.
- **Spoilage risk alert:** warns the farmer and triggers the mandi fallback when stock is close to its shelf-life limit.

**Tech stack (suggested)**
- Frontend: Flutter or React Native (mobile), React (web)
- Backend: Node.js or Python (FastAPI), REST APIs
- Database: PostgreSQL, plus Firebase for real-time updates
- AI: Python (scikit-learn, TensorFlow/PyTorch, OR-Tools)
- Maps/GPS: Google Maps API or OpenStreetMap
- Payments: UPI / payment gateway with escrow
- Cloud: AWS / Azure / GCP
- Data sources: Agmarknet / e-NAM mandi price data (verify API access)

**Accessibility for rural users**
- Regional languages (Tamil, Hindi, Telugu etc.) with voice input
- Simple UI, with SMS/WhatsApp fallback for low internet areas

**Trust and quality**
- Farmer verification (Aadhaar/FPO registration), ratings, photo-based quality grading, dispute resolution.

## Feasibility and Viability

**Technical feasibility:** All components (mobile apps, payments, maps, forecasting) use proven, available technology.

**Operational feasibility:**
- Start as a pilot in one district or region with one or two crops (e.g., vegetables, tomatoes) and onboard farmers through FPOs and Farmer Producer Companies.
- Partner with existing logistics providers instead of building a fleet.
- Link with the local APMC/market committee for the unsold-stock fallback.

**Economic viability (revenue model):**
- Small commission (e.g., 2-4%) on each order, far lower than traditional middleman margins.
- Delivery service fees and logistics partner revenue share.
- Premium analytics for FPOs and bulk buyers.

**Risks and mitigation**

| Risk | Mitigation |
|---|---|
| Low digital literacy | Local language, voice UI, FPO/agent support |
| Buyer cancels at the last moment | Advance deposit, cancellation penalty |
| Farmer cannot deliver the promised quantity | Ratings, backup farmer matching, partial fulfilment |
| Price fluctuations | AI price range, mandi fallback with a minimum expected price |
| Spoilage during transport | Shorter routes, nearby mandi, cold-chain partners later |

**Scalability:** The model can expand to more crops, districts and states, and can integrate with government platforms such as e-NAM and ONDC.

## Impact and Benefits

**Farmers**
- Higher income by removing intermediaries
- Pre-booked demand, so less uncertainty and less distress selling
- Protection from total loss through the mandi fallback

**Consumers and retailers**
- Lower prices, fresher produce and transparent pricing
- Reliable bulk supply planned a week in advance

**Supply chain**
- Less wastage and fewer idle trucks through route optimization and load pooling
- Better planning through demand forecasting

**Social and economic**
- Strengthens FPOs and rural livelihoods
- Supports food price stability and the goals of the Ministry of Consumer Affairs
- Promotes digital inclusion in rural areas

**Suggested measurable targets (for the pilot):** farmer income increase %, consumer price reduction %, post-harvest wastage reduction %, and number of farmers onboarded.

## Research and References

- e-NAM (National Agriculture Market): https://enam.gov.in
- Agmarknet (mandi price data): https://agmarknet.gov.in
- Ministry of Consumer Affairs, Food & Public Distribution: https://consumeraffairs.nic.in
- Government scheme for formation and promotion of 10,000 FPOs (Ministry of Agriculture & Farmers Welfare)
- ONDC (Open Network for Digital Commerce): https://ondc.org
- Google OR-Tools (vehicle routing): https://developers.google.com/optimization
- Prophet forecasting library: https://facebook.github.io/prophet
- Existing models to study and differentiate from: DeHaat, AgroStar, Ninjacart, Kisan Network
