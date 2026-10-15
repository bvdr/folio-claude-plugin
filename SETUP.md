# Setting up Folio

The Folio plugin talks to the user's Folio account through a remote MCP server at `https://mcp.myfolio.so/mcp`. Nothing is configured locally — no API keys, no files, no environment variables.

## What the user needs

1. A Folio account at https://myfolio.so. There is a 7-day free trial; after that the plan is $5/month.
2. At least one delivery target: a reMarkable, a Kindle, Dropbox or Google Drive. These can be connected in Folio settings, or from here:
   - `pair_remarkable` takes the one-time 8-character code from https://my.remarkable.com/device/desktop/connect. It replaces any reMarkable already connected, so check `list_targets` first.
   - `add_kindle` takes the Send-to-Kindle address (`@kindle.com` or `@free.kindle.com`). The Kindle is added with automatic delivery off; only the user can switch that on in Folio settings.
   - `start_connection` returns a link for Dropbox, Google Drive or Notion. The user opens it and approves in their browser; Claude never sees those credentials.

## Connecting

When the plugin is enabled, Claude connects to the Folio server and the user is sent to Folio's OAuth consent screen. They sign in, review the permissions Claude is asking for, and approve. Access can be revoked at any time from Folio settings.

If a tool call reports that the user is not authenticated, ask them to reconnect the Folio server rather than retrying the call.

## Checking it works

Call `get_settings` and then `list_targets`. `get_settings` returns the user's plan, timezone and Folio inbox address; `list_targets` returns the devices they can send to, by label. If `list_targets` comes back empty, the account has no delivery target yet — offer to connect one with the tools above, and do not try to send a file until they have.
