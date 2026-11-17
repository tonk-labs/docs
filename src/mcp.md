# MCP server

Connect an AI agent to your Tonk spaces. The agent gets a space of its own and works in the spaces you share with it, with the access you choose.

**Server URL:** `https://tonk.network/mcp`
**Transport:** Streamable HTTP
**Authentication:** OAuth, sign in with your Tonk account

## Connect

### Claude

**[Add Tonk to Claude](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Tonk&connectorUrl=https%3A%2F%2Ftonk.network%2Fmcp)**

The link opens Claude's Add custom connector dialog with the name and URL filled in. Confirm, then select **Connect** and sign in to Tonk.

To add it by hand: Customize > Connectors > Add custom connector, and paste `https://tonk.network/mcp`.

### ChatGPT

ChatGPT has no install link for custom apps, so add it in settings. Custom apps need developer mode, which is available on paid plans.

1. In ChatGPT, open Settings and turn on **Developer mode** (under Apps, or Security, depending on your version).
2. Create an app (**Create app** or **Add custom app**).
3. Name it `Tonk`, set the server URL to `https://tonk.network/mcp` and authentication to **OAuth**.
4. Confirm the custom app notice, create it, and sign in to Tonk.

### Other MCP clients

Add `https://tonk.network/mcp` as a remote (HTTP) MCP server and sign in when prompted.

## How access works

- **Home space.** Each connection gets its own agent with a home space where it keeps notes and drafts across conversations.
- **Granted spaces.** The agent sees no other space until you share one with it. Every grant is per space, read-only or read and write, and expires.
- **Invite links.** Give the agent a Tonk invite link and your client shows a prompt where you pick the access level before the agent joins. If your client can't show that prompt, grant the space in Tonk instead.
- **The agent is not you.** It joins spaces as its own member, not with your identity, and can only act within the access you granted.
- **Writes are explicit.** Reads never change anything. Changes go through the space's own commands and run once.

## Tools

| Tool | What it does | Changes data |
| - | - | - |
| `tonk_list_spaces` | Lists the agent's home and the spaces granted to it, with access level and expiry | No |
| `tonk_query` | Reads a space's schema, records and views | No |
| `tonk_outline` | Lists the views a space renders, with a route for each | No |
| `tonk_open_space` | Shows a space's view live in the chat, in clients that support inline UI | No (you can edit from the view in read-write spaces) |
| `tonk_join_space` | Asks you to approve joining a space from an invite link | No (joining needs your approval) |
| `tonk_evaluate` | Creates or updates records and runs the space's commands | Yes |
| `tonk_guide` | Returns the notation reference the agent uses to read and write | No |

## Revoking access

TODO: where in Tonk a person removes an agent from a space or ends a grant early. Grants also lapse on their own when they expire.

## Data and privacy

Content the agent reads from a space is sent to your AI client and its model provider, and their privacy terms apply to it. Tonk's handling of spaces, accounts and logs is covered by the [Tonk Privacy Policy](https://tonk.xyz/legal/privacy).

## Support

hello@tonk.xyz · [Discord](https://discord.gg/hBPQ9xPWF7)
