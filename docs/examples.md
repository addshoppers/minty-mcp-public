# Example Requests and Responses

The examples below were captured on June 17, 2026 from real calls to the current v2 MCP server implementation backed by the live Minty API.

For coupon-bearing tools, the examples use real no-result snapshots where possible so the repository does not publish live coupon codes while still showing the actual response shape returned by the API.

## `find_store_offers`

### Example request

```json
{
  "query": "deals for NoSuchStore987",
  "merchant": "NoSuchStore987",
  "limit": 1
}
```

### Example structured response

```json
{
  "type": "deals",
  "data": {
    "deals": [],
    "merchant": "NoSuchStore987",
    "category": null,
    "categoryQuery": null,
    "merchantLogo": null,
    "results": []
  }
}
```

Source file: [examples/find_store_offers.response.json](../examples/find_store_offers.response.json)

## `find_product_cashback`

### Example request

```json
{
  "query": "cashback for NoSuchStore987",
  "merchant": "NoSuchStore987",
  "limit": 1
}
```

### Example structured response

```json
{
  "type": "cashback",
  "data": {
    "deals": [],
    "merchant": "NoSuchStore987",
    "category": null,
    "merchantLogo": null,
    "pagination": {
      "total": 0,
      "offset": 0,
      "limit": 1,
      "hasMore": false
    },
    "results": []
  }
}
```

Source file: [examples/find_product_cashback.response.json](../examples/find_product_cashback.response.json)

## `find_coupon_codes`

### Example request

```json
{
  "query": "coupon for Target",
  "merchant": "Target",
  "limit": 1
}
```

### Example structured response

```json
{
  "type": "coupons",
  "data": {
    "coupons": [],
    "merchant": "Target",
    "category": null,
    "merchantLogo": null,
    "pagination": {
      "total": 0,
      "offset": 0,
      "limit": 1,
      "hasMore": false
    },
    "results": []
  }
}
```

Source file: [examples/find_coupon_codes.response.json](../examples/find_coupon_codes.response.json)

## Response Conventions

- The top-level object uses `type` to identify the result class.
- The payload is returned in `data`.
- Arrays such as `deals` or `coupons` contain the items most clients render directly.
- `pagination` can be used for follow-up or load-more flows when the tool includes pagination.
- `results` is the compact normalized result list returned by the v2 tools.
- Merchant inventory changes over time, so live responses may differ from these snapshots.
