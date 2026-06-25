# Minty MCP Public

Public documentation for Minty's remote Model Context Protocol (MCP) server.

This repository is the public-facing integration surface for developers who want to connect Minty to AI clients such as ChatGPT and Claude. It focuses on:

- the hosted MCP endpoint
- the Minty MCP v2 tool surface
- example requests and example structured responses captured from real MCP/API calls
- quick connection guidance

The production endpoint shown in these docs is:

```text
https://mcp.minty.com/mcp
```

If the launch URL changes, update this repository and the GitHub Pages site together.

## Contents

- [GitHub Pages docs](./docs/index.md)
- [Installation guide](./docs/index.md#install-in-chatgpt)
- [Tool catalog](./docs/tools.md)
- [Example requests and responses](./docs/examples.md)

## Repository Scope

This repository intentionally does not include Minty's internal deployment configuration, private infrastructure setup, or internal-only automation.

## Live Data

The example responses in this repository are captured from real calls against the current v2 MCP implementation backed by the live Minty API. Because deals, cashback, and coupon inventory change over time, these examples are snapshots rather than fixed contracts for merchant content.

## GitHub Pages

This repository is designed to publish documentation from the `docs/` directory using GitHub Pages.
