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
