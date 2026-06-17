# Tool Catalog

The list below reflects the tools returned by the live production endpoint on June 17, 2026.

| Tool | Use when | Main inputs | Structured output |
| --- | --- | --- | --- |
| `get_coupons_by_merchant` | The user wants coupon codes for a merchant or merchant domain | optional `merchant`, `domain_name` | `type: "coupons"` |
| `get_cashback` | The user asks for cashback by merchant, domain, category, or top merchants | optional `merchant`, `domain_name`, `category`, `offset`, `limit` | `type: "cashback"` |
| `get_all_offers_by_merchant` | The user wants all offers for a merchant, domain, or category | optional `merchant`, `domain_name`, `category`, `offset`, `limit` | `type: "deals"` |
| `get_offers_by_category` | The user wants category-scoped offers, optionally filtered by coupons or promotions | `category`, optional `offer_type`, `offset`, `limit` | `type: "deals"` |

## Notes

- `domain_name` is preferred when the merchant domain is known.
- `category` can be used for category-based discovery when no merchant is known.
- `offset` and `limit` support pagination.
- The public endpoint currently returns these `get_*` tool names. If new tool names are deployed later, update this page from a fresh `tools/list` call.
