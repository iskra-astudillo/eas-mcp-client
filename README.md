# Elite Agentic Solutions MCP client examples

The rule engine checks agent actions. A hash-chained audit trail records each action.

This repository holds small, working examples for the hosted **Elite Agentic Solutions** MCP server. It is maintained by Elite AI Empire. The server itself is hosted; nothing here runs it.

- Product: https://eliteagenticsolutions.com/
- MCP endpoint (streamable HTTP): `https://eliteagenticsolutions.com/mcp`
- OpenAPI: https://eliteagenticsolutions.com/openapi.json
- Pricing, machine readable: https://eliteagenticsolutions.com/pricing.json
- Discovery file: https://eliteagenticsolutions.com/.well-known/mcp.json

## Tools

| Tool | What it does |
|---|---|
| `eas_audit_readiness` | Takes 20 answers, each 0 (no), 1 (partly) or 2 (yes), in the order of the questions action. Returns points, the percentage score and the questions that were not |
| `eas_audit_questions` | Returns the questions in the order the readiness action expects answers. Pricing: {"unit": "call", "price_usd": 0, "free_quota": "200 per day per IP", "note": " |
| `eas_about` | What Elite Agentic Solutions does and what is free Pricing: {"unit": "call", "price_usd": 0, "free_quota": "200 per day per IP", "note": "Keyed volume pricing i |
| `eas_pricing` | Where prices live and what costs nothing Pricing: {"unit": "call", "price_usd": 0, "free_quota": "200 per day per IP", "note": "Keyed volume pricing is publishe |
| `usage_get` | Usage for the calling key (last 30 days) |
| `get_company_info` | What this company sells, who it is for, and every agent/API entry point. No account needed. |
| `list_pricing` | Current plans and prices in USD: plan, interval, amount_usd, currency, what_you_get. No account needed. |
| `get_checkout_link` | Checkout URL for a plan. With no arguments: the main paid plan. Where the site supports it the URL is a Stripe-hosted Checkout session (created unpaid; a human  |
| `search_site` | Find pages on this site by keyword; returns url, title and summary. |

## Try it

```bash
bash examples/initialize.sh
python3 examples/client.py
```

`examples/client.py` uses only the Python standard library. It sends `initialize` and `tools/list` and prints the result. No key is needed for the public read tools. Tools that need an account say so in their description.

## Registry

Listed in the official MCP registry. Server manifest: `server.json`.

## Licence

MIT. See `LICENSE`.
