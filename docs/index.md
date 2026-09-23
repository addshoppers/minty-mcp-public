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
- Grok Build plugin source files for the xAI plugin marketplace

## Supported Client Targets

- ChatGPT
- Claude
- Grok

Compatibility can vary by client version and MCP feature support. Core tool calls should rely on the MCP endpoint and structured tool results, not on any client-specific UI behavior.

## Quick Connect

Use the Minty MCP endpoint in your AI client:

```text
https://mcp.minty.com/mcp
```

If your client asks for a server URL, use the endpoint above directly.

## How To Use

Minty MCP can be added manually to supported AI clients by using the remote server URL below. This repository also includes Grok Build plugin source files that point to the same hosted MCP endpoint.

```text
https://mcp.minty.com/mcp
```

After adding the server, start a new chat or session and try prompts such as:

- `Find store offers for Target`
- `What cashback is available for beauty products?`
- `Find coupon codes for Sephora`

## Result Clicks And Sign-In

Minty MCP lookups are free and anonymous. The tools can return current coupons, cashback, and store offers without requiring a Minty sign-in inside ChatGPT, Claude, or Grok.

The tools themselves are unauthenticated, so lookup requests do not include a Minty user session. Results are not personalized, and the tools do not expose shopper balance, order history, cashback history, or account-specific recommendations.

When a shopper clicks a cashback, offer, or coupon result, the click routes through the Minty web interstitial before continuing to the merchant. The interstitial asks the shopper to sign in with an email address so Minty can attribute the shopping session. After sign-in, Minty sends the shopper to the merchant.

Cashback can only be credited after the shopper signs in through Minty and completes the qualifying merchant purchase flow.

## Client Plan Availability

In the current tested setup, Minty MCP can be connected manually from logged-in Free accounts in ChatGPT and Claude. Grok custom connector availability can vary by account rollout, workspace policy, region, and client surface.

- ChatGPT: sign in, enable Developer mode in Plugins, then add Minty manually.
- Claude: sign in and add Minty as a custom connector. Claude Free may be limited to one custom connector.
- Grok: sign in, click `Plugins` to open the `Connectors` popup, then add Minty as a custom connector.

Publishing to the Grok Build plugin marketplace is a separate GitHub PR-based flow and does not require a paid Grok Bot seat. Grok Bot template testing is separate from the plugin marketplace and may require a paid Cursor or SuperGrok-linked account depending on the test surface.

Availability can vary by account rollout, workspace policy, region, and client surface.

## Install In ChatGPT

In the current ChatGPT UI, the setup flow is:

1. Open ChatGPT and sign in.
2. Go to `Settings`.
3. Open `Plugins`.
4. Open `Developer mode`.
5. Enable `Developer mode`.
6. Return to `Plugins`.
7. Click the `+` button in the top-right of the Plugins page.
8. In the `New App` form, fill these fields:
   - `Name`: `Minty`
   - `Description`: optional, for example `Coupons, cashback, and store offers`
   - `Connection`: choose `Server URL`
   - `Authentication`: choose `No Auth`
9. Paste this server URL into the `Server URL` field:

```text
https://mcp.minty.com/mcp
```

10. Check the confirmation box under the custom MCP server warning.
11. Click `Create`.
12. Start a new chat and test with prompts such as:
   - `Help me find shopping savings for home decor`
   - `What cashback is available for beauty?`
   - `Find coupon codes for Pizza Hut`

You can open `Plugins` from the left sidebar or from `Settings` -> `Plugins`.

If you do not see `Plugins`, `Developer mode`, or the top-right `+` button, confirm that you are signed in and Developer mode is enabled. Availability may also vary by rollout, region, workspace policy, or client surface.

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

If you do not see `Connectors` or `Add custom connector`, confirm that you are signed in. On Claude Free, remove another custom connector if you have already used the one-connector limit. Availability may also vary by rollout, region, or workspace policy.

## Install In Grok

In the current Grok UI, the setup flow is:

1. Open Grok and sign in.
2. Click `Plugins` to open the `Connectors` popup.
3. Click `New Connector`.
4. Choose `Custom`.
5. In the connector form, fill these fields:
   - `Name`: `Minty`
   - `Server URL`: paste the URL below
   - `Authentication`: choose `No Auth` if prompted
6. Paste this server URL:

```text
https://mcp.minty.com/mcp
```

7. Save the connector.
8. Start a new chat and test with prompts such as:
   - `Help me find shopping savings for home decor`
   - `What cashback is available for beauty?`
   - `Find coupon codes for Pizza Hut`

If you use Grok Business or Enterprise and do not see custom connectors, your workspace admin may need to provision the connector first.

## Documentation

- [Tool catalog](./tools.md)
- [Example requests and responses](./examples.md)

## Tool Set

This public documentation focuses on the 3 v2 tools:

1. `find_store_offers`
2. `find_product_cashback`
3. `find_coupon_codes`

## Troubleshooting

- If ChatGPT, Claude, or Grok does not show any Minty tools after setup, start a new chat or session and try again.
- If your client rejects the server URL, verify that you entered `https://mcp.minty.com/mcp` exactly.
- If ChatGPT does not expose custom MCP setup, confirm that Developer mode is enabled in Plugins.
- If Claude reports connection failures, remove the custom connector and add it again with the exact server URL.
- If Grok reports connection failures, remove the connector and add it again with the exact server URL. For local development, expose the local MCP server through a public HTTPS tunnel before adding it to Grok.
- If Grok Business or Enterprise does not show the Minty connector, ask your workspace admin to enable or provision custom MCP connectors.
- If a clicked result asks for an email sign-in on Minty, that is expected. Lookup is anonymous, but earning cashback requires sign-in.
- If results are not personalized or do not include balance or order history, that is expected because the public MCP tools are unauthenticated.
