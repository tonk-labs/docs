# MCP server

Connect an AI agent to your Tonk spaces. The agent gets a space of its own and works in the spaces you share with it, with the access you choose.

**Server URL:** `https://tonk.network/mcp`
**Transport:** Streamable HTTP
**Authentication:** OAuth. You approve each connection in Tonk with your passkey.

## Connect

### Claude

**[Add Tonk to Claude](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Tonk&connectorUrl=https%3A%2F%2Ftonk.network%2Fmcp)**

The link opens Claude's Add custom connector dialog with the name and URL filled in. Confirm, then select **Connect** and approve the agent in Tonk.

To add it by hand: Customize > Connectors > Add custom connector, and paste `https://tonk.network/mcp`.

### ChatGPT

ChatGPT has no install link for custom apps, so add it in settings. Custom apps need developer mode, which is available on paid plans.

1. In ChatGPT, open Settings and turn on **Developer mode** (under Apps, or Security, depending on your version).
2. Create an app (**Create app** or **Add custom app**).
3. Name it `Tonk`, set the server URL to `https://tonk.network/mcp` and authentication to **OAuth**.
4. Confirm the custom app notice, create it, and approve the agent in Tonk.

### Other MCP clients

Add `https://tonk.network/mcp` as a remote (HTTP) MCP server and approve the agent in Tonk when prompted.

## How access works

- **Home space.** When you approve a connection you create a new agent or reconnect an existing one. Each agent has a home space of its own, where it saves what you ask it to keep.
- **Granted spaces.** The agent sees no other space until you share one with it. Every grant is per space, read-only or read and write, and expires with the invite link or after 90 days, whichever comes first.
- **Invite links.** Give the agent a Tonk invite link and your client shows a prompt where you pick the access level before the agent joins. If your client can't show that prompt, grant the space in Tonk instead.
- **The agent is not you.** It acts as itself, under its own name, and can only do what its access allows. A read-only agent's writes are refused by the space, whatever the model asks for.
- **Writes are explicit.** Reads never change anything. Each write runs at most once and is never replayed automatically; if a reply is lost, the agent checks the space before trying again. Every change is recorded in the space's history.

## Tools

| Tool | What it does | Changes data |
| - | - | - |
| `tonk_list_spaces` | Lists the agent's home and the spaces granted to it, with access level and expiry | No |
| `tonk_query` | Reads a space's schema, records and views, written in [Tonk notation](notation.md) | No |
| `tonk_outline` | Lists the views a space renders, with a route for each | No |
| `tonk_open_space` | Shows a space's view live in the chat, in clients that support inline UI | No (you can edit from the view in read-write spaces) |
| `tonk_join_space` | Asks you to approve joining a space from an invite link | No (joining needs your approval) |
| `tonk_evaluate` | Creates or updates records and runs the space's commands, written in [Tonk notation](notation.md) | Yes |
| `tonk_guide` | Returns the manuals the agent uses to read and write, including the [notation reference](notation.md) | No |

## Removing access

Open **your agents** in Tonk and remove the agent's access to a space, or remove the agent altogether. Removing asks for your passkey.

Removing an agent does not end the invite link it joined with: whoever has the link can still use it. Grants also lapse on their own when they expire.

## Data and privacy

Content the agent reads from a space is sent to your AI client and its model provider, and their privacy terms apply to it. Tonk's handling of spaces, accounts and logs is covered by the [Tonk Privacy Policy](https://tonk.xyz/legal/privacy).

## Support

hello@tonk.xyz · [Discord](https://discord.gg/hBPQ9xPWF7)
