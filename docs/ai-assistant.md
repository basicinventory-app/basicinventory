# AI assistant

Ask about your inventory in plain language instead of building a filter.

The assistant is **optional and off until you set it up**. BasicInventory ships
no API key: you connect your own AI provider account, and that provider bills you
directly for what you ask.

## What it can answer

Real questions, answered from your data:

- *Which items are below their minimum stock?*
- *What expires in the next 30 days?*
- *Where is lot L26061?*
- *How many units of each category do I have?*
- *What moved yesterday?*
- *Which items have no stock at all?*
- *Summarise the state of the warehouse.*

It can group, count, compare and cross-reference — it writes its own read-only
query against your inventory tables rather than being limited to a fixed list of
canned questions.

## What it cannot do

- **Change anything.** It is strictly read-only: no entries, no exits, no edits,
  no deletions. Actions that change data are designed for but not built, and
  would be explicit and confirmable.
- **See your configuration or credentials.** API keys, settings, backups, file
  paths and system internals are outside the data it can reach — enforced by an
  allowlist of inventory tables, not by a polite instruction in a prompt.
- **Work offline.** Your question goes to your provider over the internet.

## Setting it up

**AI assistant → Configuration → Add provider.**

| Provider | Where to get a key |
| --- | --- |
| OpenAI | https://platform.openai.com |
| Anthropic (Claude) | https://platform.claude.com |
| Google Gemini | https://ai.google.dev |
| OpenRouter | https://openrouter.ai |

1. Pick the provider.
2. Paste your API key.
3. Leave the recommended model, or choose another. Any model identifier can be
   typed in, and a custom endpoint and extra parameters are available under
   **Advanced options** — so a model released tomorrow works without waiting for
   an update.
4. Save. **The connection is tested first**: an invalid key, model or endpoint is
   never stored, and the reason is shown.

Several providers can be configured at once, with one marked active; switch
between them from the chat.

## What it costs

Nothing to BasicInventory, and something to your provider. Each question spends
credit on your account at your provider's rates — the screen says so, and the
notice is always visible, not just the first time.

Two habits keep it cheap: prefer the recommended (smaller) model for everyday
questions, and start a new conversation when you change subject, since the
history of a conversation is re-sent with each question.

## Conversations

The assistant keeps a history, like any chat tool: several conversations at once,
a new one whenever you want, and old ones to return to. They are stored in your
local database and can be deleted individually.

The last twenty turns of the open conversation are re-sent with each question so
it can follow up; older turns stay in your history but are not re-sent.

## Boxes or pallets

The assistant follows your management mode. In **boxes** mode it never mentions
pallets or SSCC codes and talks about goods in locations; in **pallets** mode it
uses them freely. Change the mode in Settings and the next answer follows.

## Privacy

When you ask a question, the following goes to **the provider you configured**:

- your question and the conversation so far,
- the inventory data needed to answer it (item names, quantities, locations,
  lots, dates — whatever the question touches).

Nothing goes to BasicInventory, and nothing goes anywhere else. Your API key is
stored encrypted (AES-256-GCM) with a key kept outside the database, and the
application only ever displays a masked hint of it.

If your inventory data is sensitive enough that it must not reach a third party,
simply do not configure the assistant: every other feature works without it.

## Troubleshooting

**"Invalid API key"** — regenerate it at the provider and paste it again; keys
are often truncated when copied.

**"Model not found"** — the identifier does not exist for your account, or your
plan lacks access. Try the recommended model.

**"Quota exceeded"** — your provider account is out of credit. That is between
you and them; BasicInventory does not resell access.

**"Could not connect"** — no internet, or a firewall is blocking the provider's
domain.

**Answers look wrong** — check the management mode and, if a lot or item name is
involved, spell it exactly as it appears in your data. Persistently wrong answers
are worth a [bug report](https://github.com/basicinventory-app/basicinventory/issues/new?template=bug_report.yml)
with the question and the answer.
