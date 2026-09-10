# Setting up Folio

The Folio plugin talks to the user's Folio account through a remote MCP server at `https://myfolio.so/mcp`. Nothing is configured locally — no API keys, no files, no environment variables.

## What the user needs

1. A Folio account at https://myfolio.so. There is a 7-day free trial; after that the plan is $5/month.
2. At least one delivery target connected in Folio settings — a reMarkable, a Kindle, Dropbox or Google Drive. Targets are connected in the Folio web app, not from here.

## Connecting

When the plugin is enabled, Claude connects to the Folio server and the user is sent to Folio's OAuth consent screen. They sign in, review the permissions Claude is asking for, and approve. Access can be revoked at any time from Folio settings.

If a tool call reports that the user is not authenticated, ask them to reconnect the Folio server rather than retrying the call.

## Checking it works

Call `get_settings` and then `list_targets`. `get_settings` returns the user's plan, timezone and Folio inbox address; `list_targets` returns the devices they can send to, by label. If `list_targets` comes back empty, the account has no delivery target yet — point the user at https://myfolio.so/help to connect one, and do not try to send a file until they have.
