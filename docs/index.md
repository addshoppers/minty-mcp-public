# Minty MCP

Minty MCP is a remote Model Context Protocol server for shopping assistance. It helps AI clients find:

- coupon codes
- cashback opportunities
- store offers and promotions

## Endpoint

```text
https://mcp.minty.com/mcp
```

## What You Get

- A remote MCP server that can be added to supported AI clients
- A focused toolset for coupons, cashback, and promotional offers
- Structured responses that are easy for MCP-compatible clients to render or summarize

## Supported Client Targets

- ChatGPT
- Claude

Compatibility can vary by client version and MCP feature support. Core tool calls should rely on the MCP endpoint and structured tool results, not on any client-specific UI behavior.

## Quick Connect

Use the Minty MCP endpoint in your AI client:

```text
https://mcp.minty.com/mcp
```

If your client asks for a server URL, use the endpoint above directly.

## Documentation

- [Tool catalog](./tools.md)
- [Example requests and responses](./examples.md)

## Public Tool Set

The production endpoint currently exposes these tool names:

1. `get_coupons_by_merchant`
2. `get_cashback`
3. `get_all_offers_by_merchant`
4. `get_offers_by_category`

This page reflects the deployed public endpoint, not unreleased local development branches.
