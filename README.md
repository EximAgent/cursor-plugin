# EximAgent plugin

Trade intelligence for exporters and importers, inside your AI assistant.

Ask in plain words, and your assistant uses [EximAgent](https://eximagent.ai) to:

- find importers, buyers and distributors from real customs shipment records
- look up HS codes, tariffs and duties for a trade lane
- screen company or person names against the OFAC sanctions list
- research a company from its website
- draft outreach emails that are **only sent after you say yes**

Every result says how sure it is: verified, extracted, heuristic or inferred.

## What's inside

| Part | What it does |
| --- | --- |
| `mcp.json` | Connects to the hosted EximAgent connector at `https://mcp.eximagent.ai/mcp` (streamable HTTP, OAuth sign-in) |
| `skills/eximagent` | Teaches the assistant to connect first, ask before guessing, preview anything that costs credits, and never send outreach without your yes |

## Set up (about 2 minutes)

You need an EximAgent account. There's a free plan and no card is needed. See [pricing](https://eximagent.ai/pricing).
You sign in with Google. There's no API key to copy or paste.

### Cursor

1. Install **EximAgent** from the Cursor Marketplace.
2. Open the plugin's `eximagent` server and choose **Connect** (or **Authenticate**).
3. Sign in with Google in the browser window that opens.

### Grok Bot

1. Open **Connect Apps** (formerly Marketplace) in the sidebar, find **EximAgent**, and choose **Add**.
2. Choose **Authorize** and sign in with Google in your browser.
3. In a chat, type `@` and pick EximAgent to attach it to a task.

If EximAgent doesn't show up in Connect Apps yet, ask your Bot:
"Add a custom MCP server called eximagent at https://mcp.eximagent.ai/mcp". Then sign in from the connect card.

### Other assistants

- **Claude Code:** `claude mcp add --transport http eximagent https://mcp.eximagent.ai/mcp --scope user`, then run `/mcp` to sign in.
- **Codex:** `codex mcp add eximagent --url https://mcp.eximagent.ai/mcp`, then `codex mcp login eximagent`.
- **Claude desktop or web:** Settings → Connectors → Add custom connector → `https://mcp.eximagent.ai/mcp`.

Full connector guide: https://eximagent.ai/docs/integrations/mcp

## Try it

- "Which companies import green coffee into Germany? Show the scope and evidence behind the ranking."
- "What HS code fits frozen shrimp?"
- "What duty applies to coffee shipped from Vietnam to Germany?"
- "Screen these three company names against sanctions."
- "Find importers of my product in Germany, shortlist the best five, and draft a first email to each. Don't send anything."

## What it can change, and what it can't

- Lookups (HS codes, tariffs, sanctions, trade questions) only read data.
- Starting a buyer search, saving lists, enriching contacts, and drafting or sending emails change your account and can
  use credits. The assistant is told to preview these and wait for your yes.
- Emails are never sent unless you confirm. The service refuses to send to a sanctions-matched recipient.
- Sanctions results are advisory. The final decision is yours.
- The connector reads the account you sign in with and the EximAgent trade data. It does not read your files, your mail
  or your other connectors.
- To disconnect, use your assistant's sign-out or remove-connector control. Removing the connector doesn't delete your
  saved EximAgent data.

## Help

- Docs: https://eximagent.ai/docs
- Support: support@eximagent.ai
- Command-line tool (for developers): https://github.com/EximAgent/cli

## License

The files in this repository (manifest, MCP config, skill and README) are released under the MIT License. See
[LICENSE](LICENSE).
Using the EximAgent service is governed by the [EximAgent Terms](https://eximagent.ai/policies/terms) and
[Privacy Policy](https://eximagent.ai/policies/privacy).
