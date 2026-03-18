# Marketplace Tracking Architecture 💍

This repository contains the technical tracking architecture and Proof of Concept (PoC) developed for the weddings marketplace project. The implementation demonstrates a professional-grade data pipeline focusing on **Identity Resolution**, **eCommerce Funnels**, and **Data Governance**.

---

## 🚀 Core Features

* **Privacy-First Identity Resolution:** Implemented a robust `identify` layer to tie anonymous behavioral data to persistent user profiles using Segment.
* **eCommerce Schema Alignment:** Mapped custom business events (Vendor Discovery) to standard GA4 eCommerce protocols (`view_item`, `add_to_cart`) to unlock native reporting.
* **Scalable Architecture:** Built a "Source-Agnostic" pipeline where data is collected once and routed to multiple destinations without additional code.
* **Zero-Loss Data Integrity:** Configured strict initialization triggers (`Set Configuration Fields`) to ensure 100% accurate session attribution.

---

## 🛠 Technical Implementation

### 1. Persistent Identity Layer
Using the `analytics.identify` method, we capture high-value business traits. This transforms simple traffic into actionable user segments.

```javascript
analytics.identify('USER_ID_1000236', {
  email: 'david@example.com',
  wedding_date: '2027-05-05',
  wedding_budget: 25000,
  member_type: 'Bride',
  guest_count: 150
});
