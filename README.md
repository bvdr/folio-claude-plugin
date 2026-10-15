# Folio for Claude

Folio is a read-later service that turns saved articles, newsletters and written text into typeset PDFs and EPUBs and delivers them to a reMarkable, Kindle, Dropbox or Google Drive.

This plugin gives Claude access to a Folio account, so a piece of work can end on the device instead of on the screen. Claude can save a link for later, read through what is already in the inbox, write a brief and send it to a reMarkable, draw a planner for the pen, and set up a weekly delivery.

## What you need

- A Folio account at [myfolio.so](https://myfolio.so) — 7-day free trial, then $5/month
- At least one delivery target connected in Folio settings: a reMarkable, a Kindle, Dropbox or Google Drive

## Install

```
/plugin install folio@claude-community
```

On first use Claude connects to Folio's MCP server at `https://mcp.myfolio.so/mcp` and sends you to Folio's consent screen. Sign in, review what Claude is asking for, approve. You can revoke access any time from your Folio settings.

## Try it

- "Send our conversation to my reMarkable as a PDF."
- "What's in my Folio inbox?"
- "Research heat pumps and send the brief to my Kindle."
- "Save https://example.com/article for later."
- "Make me a weekly planner I can write on, and send it to my reMarkable."
- "Every Friday at 8am, gather what I saved this week into an issue and send it."

## What's inside

Six skills, each covering one thing you would ask for:

| Skill | What it covers |
|---|---|
| `save-to-folio` | Saving a link or a piece of writing to the inbox |
| `read-the-inbox` | Listing, searching and reading what you already saved |
| `research-and-send` | Writing a brief or summary and delivering it as a PDF |
| `send-to-device` | Sending a PDF or EPUB you produced to a device |
| `write-on-templates` | Planners, trackers and note layouts drawn for the pen, using our catalogue at [einktemplates.net](https://einktemplates.net) |
| `set-up-routines` | RSS subscriptions and recurring deliveries |

They run against the Folio MCP server, which exposes read tools for your inbox, issues, feeds, schedules and delivery targets, and write tools for saving, rendering and sending. Read tools are annotated read-only; tools that remove or replace something are annotated destructive, so Claude asks before running them.

## Privacy

Folio only sees what you send it. The [privacy policy](https://myfolio.so/privacy) covers what is collected, how long it is kept and who processes it, including a section on AI assistant connections.

Support: [hello@myfolio.so](mailto:hello@myfolio.so) · [Help centre](https://myfolio.so/help)

## License

MIT — see [LICENSE](./LICENSE).
