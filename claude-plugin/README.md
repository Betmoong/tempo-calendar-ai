# Tempo Calendar Plugin for Claude Code

Ask Claude Code about your schedule, or have it add and change events and tasks in Tempo Calendar on your Mac.

## Prerequisites

- Tempo Calendar for Mac with AI Integration
- Claude Code

## Installation

1. In Tempo, open **Settings > AI Integration** and turn it on.
2. Under **Connected AI Tools**, click **How to Connect** next to Claude Code. Then click **Copy Token Only**.
3. Run `/plugin install tempo-calendar@claude-plugins-official` and paste the token when Claude Code asks for it. Leave the address as is unless you changed the port in Tempo.
4. Run `/mcp` in Claude Code and check that `tempo` is connected.

To change the token or the address later, open `/plugin`, select Tempo Calendar on the **Installed** tab and choose **Configure options**.

## Examples

- "What's on my calendar this week? Leave out the holidays."
- "Book a design review tomorrow at 3 PM on my Work calendar and put the meeting link in the notes."
- "Move Friday's dinner to Saturday at the same time."
- "Add a 'Watch a movie' event on November 5 and a 'Book movie tickets' task."

## Available tools

| Tool | What it does |
| --- | --- |
| `list_calendars` | Calendars you allowed, and which ones can be edited |
| `find_events` | Search events by date range, text or calendar |
| `get_event` | Everything about one event, including notes |
| `create_event`, `update_event` | Title, time, all-day, calendar, location, link, notes, alarms, repeat |
| `delete_event` | Deletes one event. It stays in Tempo's Trash for 30 days |
| `list_reminder_groups` | Task lists you allowed |
| `find_reminders`, `get_reminder` | Search and read tasks |
| `create_reminder`, `update_reminder` | Title, list, due date, notes, link, priority, repeat, completion |
| `delete_reminder` | Deletes one task |

In Tempo's AI Integration settings you choose how much Claude can do and which calendars and task lists it can see. Every change shows up in Tempo's AI activity window, where you can undo most of them.

## Privacy

The plugin runs no code of its own. It tells Claude Code to send MCP requests with your token to the server inside Tempo on your Mac (127.0.0.1). That server stops when you quit Tempo and rejects requests without the token. Disconnecting Claude Code in Tempo revokes it.

Anything Claude reads from Tempo, such as an event title or a task's notes, becomes part of your Claude conversation and is sent to Anthropic with the rest of it.

As the developer, I never see your events or tasks. Tempo's app analytics record each tool call and whether it worked, along with which AI tool made it. Nothing you wrote in Tempo goes into them.

## Troubleshooting

If Claude Code can't connect, open Tempo and make sure AI Integration is on. The status in Tempo's settings should read **Ready for connections**.

If the token is rejected, copy it again in Tempo and paste it into the plugin's options. After Claude Code has connected once, **How to Connect** is in the **…** menu next to it.

If Tempo shows **Another app is using this port**, enter a different port in the Port field under the status. Then update the address in the plugin's options to match.

## License

MIT
