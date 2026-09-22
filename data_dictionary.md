# Panther Provisions — Data Dictionary

*Maintained by the Analytics team. Last reviewed: Q2 FY2024.*

Panther Provisions is a direct-to-consumer retailer serving the Pittsburgh
metro area. The extracts below are pulled from the order management system and
the customer master.

---

## channel_test.csv

One row per website visitor from a two-channel media test.

| Column | Type | Description |
|---|---|---|
| `visitor_id` | text | Unique visitor identifier |
| `channel` | text | Channel that delivered the visit |
| `visitor_type` | text | `new` or `returning` |
| `converted` | integer | `1` if the visit resulted in an order, else `0` |

## channel_spend.csv

| Column | Type | Description |
|---|---|---|
| `channel` | text | Channel name |
| `media_spend_usd` | integer | Total media spend for the test period, USD |

---
## panther_orders_messy.csv

One row per order.

| Column | Type | Description |
|---|---|---|
| `order_id` | text | Unique order identifier, format `PP-######` |
| `customer_id` | integer | Foreign key to the customer master |
| `order_date` | date | Date the order was placed |
| `ship_date` | date | Date the order shipped from the warehouse |
| `channel` | text | Acquisition channel: Email, Paid Social, Organic, Retargeting |
| `region` | text | Sales region rollup |
| `state` | text | Two-letter state code |
| `quantity` | integer | Units ordered |
| `unit_price` | decimal | Price per unit in USD |
| `revenue` | decimal | Extended order revenue (quantity × unit_price) |
| `returned` | text | `Y` / `N` flag indicating a return was processed |
| `satisfaction_score` | integer | Post-purchase survey response, 1–5 scale |

## panther_customers.csv

One row per customer.

| Column | Type | Description |
|---|---|---|
| `customer_id` | integer | Primary key |
| `address_line` | text | Street address |
| `city` | text | City |
| `state` | text | Two-letter state code |
| `effective_start` | date | Date this record became active |
| `effective_end` | date | Date this record was superseded; blank if current |
| `loyalty_tier` | text | Bronze / Silver / Gold / Platinum |
| `customer_age` | integer | Customer age in years |
| `signup_date` | date | Date of first account creation |

---

### Known issues

Some historical records were migrated from the legacy platform in 2023 and may
contain formatting inconsistencies. Contact the Analytics team with questions.
