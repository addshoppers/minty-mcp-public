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
- A focused v2 toolset for coupons, cashback, and promotional offers
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

## How To Use

Minty MCP can be added manually to supported AI clients by using the remote server URL below:

```text
https://mcp.minty.com/mcp
```

After adding the server, start a new chat or session and try prompts such as:

- `Find store offers for Target`
- `What cashback is available for beauty products?`
- `Find coupon codes for Sephora`

## Install In ChatGPT

In the current ChatGPT UI, the setup flow is:

1. Open ChatGPT.
2. Go to `Settings`.
3. Open `Apps`.
4. Click `Create app`.
5. In the `New App` form, fill these fields:
   - `Name`: `Minty`
   - `Description`: optional, for example `Coupons, cashback, and store offers`
   - `Connection`: choose `Server URL`
   - `Authentication`: choose `No Auth`
6. Paste this server URL into the `Server URL` field:

```text
https://mcp.minty.com/mcp
```

7. Check the confirmation box under the custom MCP server warning.
8. Click `Create`.
9. Start a new chat and test with prompts such as:
   - `Help me find shopping savings for home decor`
   - `What cashback is available for beauty?`
   - `Find coupon codes for Pizza Hut`

If you do not see `Apps` or `Create app`, your current ChatGPT plan or account rollout may not support custom MCP connections yet.

## Install In Claude

In the current Claude UI, the setup flow is:

1. Open Claude.
2. Go to `Settings`.
3. Open `Connectors`.
4. Click `Add`.
5. Choose `Add custom connector`.
6. In the `Add custom connector` form, fill these fields:
   - `Name`: `Minty`
   - `Remote MCP server URL`: paste the URL below
7. Paste this server URL:

```text
https://mcp.minty.com/mcp
```

8. If needed, expand `Advanced settings` and leave defaults unless your workspace requires something specific.
9. Click `Add`.
10. Start a new chat and test with prompts such as:
   - `Help me find shopping savings for home decor`
   - `What cashback is available for beauty?`
   - `Find coupon codes for Pizza Hut`

If you do not see `Connectors` or `Add custom connector`, the feature may still be in beta or unavailable for your current Claude account/workspace.

## Documentation

- [Tool catalog](./tools.md)
- [Example requests and responses](./examples.md)

## Tool Set

This public documentation focuses on the 3 v2 tools:

1. `find_store_offers`
2. `find_product_cashback`
3. `find_coupon_codes`

## Troubleshooting

- If ChatGPT or Claude does not show any Minty tools after setup, start a new chat or session and try again.
- If your client rejects the server URL, verify that you entered `https://mcp.minty.com/mcp` exactly.
- If your ChatGPT account does not expose custom MCP setup, the feature may not be enabled for your plan or rollout yet.
- If Claude reports connection failures, remove the custom connector and add it again with the exact server URL.
