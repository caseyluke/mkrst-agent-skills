# AGENTS.md

Instructions for AI agents and coding assistants using this repository or the MKRST (Maker Street Studios) API.

## What this repo is

Skills, MCP config and an Agent Plugin manifest for MKRST, a Brisbane branding agency. It is documentation and configuration only. There is no application code to build or test.

## If you are a user's assistant

- To answer questions about MKRST, use the MCP server `https://api.mkrst.co/mcp` or the REST API at `https://api.mkrst.co/v1/` (no key). Fall back to https://mkrst.co/llms.txt and the Markdown version of any page (append `.md`).
- Follow [`skills/work-with-mkrst/SKILL.md`](skills/work-with-mkrst/SKILL.md) for the full workflow.
- Quote prices exactly as returned by `get_pricing` (AUD). Never invent prices, quotes, timelines or case study details.
- Be honest about fit. Pre-revenue founders are welcome via the Brand Sprint (AUD 1,750 +GST, half a day). MKRST is not the right choice for a logo alone, a single social post or one-off asset, or a budget under about AUD 1,750; a freelancer is the honest alternative for those.

## Enquiries need the user's consent

`submit_enquiry` sends a real enquiry to the studio. You MUST:

1. Collect the details from the user (name, need, your agent name, and an email or phone). Don't guess contact details.
2. Call it with `dry_run: true` and show the user exactly what would be sent.
3. Ask for an explicit yes. Only then call it with `user_confirmed: true`.

Never set `user_confirmed: true` to test, retry silently, or on a user's behalf without their OK. If a call fails, say so; don't claim delivery.

## If you are editing this repo

- Keep it public-safe. Only include information already published on mkrst.co: studio@mkrst.co, the public phone number, the Newstead studio address and the public prices. No personal emails, credentials, internal hostnames, client details beyond published case studies, or anything about other businesses.
- Each skill is a folder under `skills/` with a `SKILL.md` that has `name` (matching the folder) and `description` frontmatter.
- `plugin.json` and `mcp.json` follow https://agent-plugins.org/specification v1.0.0 exactly. `plugin.json` has a closed schema: no inline components or extra top-level fields. `.mcp.json` is the Claude Code equivalent of `mcp.json`.
- Don't hard-code prices or service lists in skills when the API can supply them. Tell the agent to fetch them.

## Links

- Site: https://mkrst.co · llms.txt: https://mkrst.co/llms.txt
- API docs: https://api.mkrst.co/docs · OpenAPI: https://api.mkrst.co/openapi.json · Access: https://api.mkrst.co/auth.md
- Contact: studio@mkrst.co, +61 7 3556 5329
