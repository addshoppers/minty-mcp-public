# Example Requests and Responses

The examples below were captured from the live production endpoint on June 17, 2026.

For coupon-bearing tools, the examples use real no-result snapshots where possible so the repository does not publish live coupon codes while still showing the actual response shape returned by the API.

## `get_cashback`

### Example request

```json
{
  "merchant": "Adidas",
  "limit": 1
}
```

### Example structured response

```json
{
  "type": "cashback",
  "data": {
    "deals": [
      {
        "merchantId": "6354d0ae-552d-48ba-8ee9-5264cf928706",
        "merchant": "adidas",
        "webInterstitialLink": "https://www.minty.com/int?m=6354d0ae-552d-48ba-8ee9-5264cf928706",
        "cashbackRate": "0%",
        "cashbackText": "up to $0 Cashback",
        "description": "Get up to $0 Cashback at adidas",
        "affiliateLink": "https://click.minty.com/int?m=6354d0ae-552d-48ba-8ee9-5264cf928706",
        "logoUrl": "https://assets.minty.com/api-assets/merchant/adidas-com/logo/95ff7885-dea3-4410-adad-82e180b2c6af.png",
        "isTop": false,
        "isVerified": false
      }
    ],
    "merchant": "adidas",
    "category": null,
    "categoryQuery": null,
    "merchantLogo": "https://assets.minty.com/api-assets/merchant/adidas-com/logo/95ff7885-dea3-4410-adad-82e180b2c6af.png",
    "pagination": {
      "total": 1,
      "offset": 0,
      "limit": 1,
      "hasMore": false
    }
  }
}
```

Source file: [examples/get_cashback.response.json](../examples/get_cashback.response.json)

## `get_all_offers_by_merchant`

### Example request

```json
{
  "merchant": "Target",
  "limit": 1
}
```

### Example structured response

```json
{
  "type": "deals",
  "data": {
    "deals": [],
    "merchant": "Target",
    "category": null,
    "categoryQuery": null,
    "merchantLogo": "https://assets.minty.com/api-assets/merchant/target-com/logo/d46e3441-b8a6-42b8-82a7-ddd35e554122.jpg",
    "pagination": {
      "total": 0,
      "offset": 0,
      "limit": 1,
      "hasMore": false
    }
  }
}
```

Source file: [examples/get_all_offers_by_merchant.response.json](../examples/get_all_offers_by_merchant.response.json)

## `get_coupons_by_merchant`

### Example request

```json
{
  "merchant": "Target"
}
```

### Example structured response

```json
{
  "type": "coupons",
  "data": {
    "coupons": [],
    "merchant": "Target",
    "merchantLogo": "https://assets.minty.com/api-assets/merchant/target-com/logo/d46e3441-b8a6-42b8-82a7-ddd35e554122.jpg"
  }
}
```

Source file: [examples/get_coupons_by_merchant.response.json](../examples/get_coupons_by_merchant.response.json)

## `get_offers_by_category`

### Example request

```json
{
  "category": "laptops",
  "offer_type": "promotion",
  "limit": 1
}
```

### Example structured response

```json
{
  "type": "deals",
  "data": {
    "deals": [],
    "merchant": "laptops",
    "category": "laptops",
    "categoryQuery": "laptops",
    "offerType": "promotion",
    "merchantLogo": null,
    "pagination": {
      "total": 0,
      "offset": 0,
      "limit": 1,
      "hasMore": false
    }
  }
}
```

Source file: [examples/get_offers_by_category.response.json](../examples/get_offers_by_category.response.json)

## Response Conventions

- The top-level object uses `type` to identify the result class.
- The payload is returned in `data`.
- Arrays such as `deals` or `coupons` contain the items most clients render directly.
- `pagination` can be used for follow-up or load-more flows when the tool includes pagination.
- Merchant inventory changes over time, so live responses may differ from these snapshots.
