# Tool Catalog

The list below documents the 3 v2 Minty MCP tools.

| Tool | Use when | Main inputs | Structured output |
| --- | --- | --- | --- |
| `find_store_offers` | The user wants store offers, promos, or merchant deals | `query`, optional `merchant`, `domain_name`, `category`, `offset`, `limit` | `type: "deals"` |
| `find_product_cashback` | The user asks about cashback for a product, brand, merchant, or category | `query`, optional `merchant`, `brand`, `domain_name`, `category`, `offset`, `limit` | `type: "cashback"` |
| `find_coupon_codes` | The user wants promo codes, coupon codes, or checkout savings | `query`, optional `merchant`, `domain_name`, `category`, `offset`, `limit` | `type: "coupons"` |

## Notes

- `domain_name` is preferred when the merchant domain is known.
- `category` can be used for category-based discovery when no merchant is known.
- `offset` and `limit` support pagination.
- The example responses in this repository were captured from real calls through the current v2 MCP server implementation on June 17, 2026.
