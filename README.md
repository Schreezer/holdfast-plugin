# Daybond for Claude

[Daybond](https://holdfast-site.chiragmgg.workers.dev) is a free iOS app for hard daily challenges, alone or with a crew. This plugin connects Claude to it. Daybond used to be called Holdfast. The plugin, skill and server names keep the old name, so existing installs and connections keep working.

- **Check in:** "Did my run and read 20 pages." Claude logs today's tasks you tell it about, asks when something's vague, and never ticks anything you didn't say you did.
- **Design:** Claude interviews you and drafts a challenge. You review and create it in the app.
- **Review:** streaks, misses, the task that keeps slipping, and one change to try next.
- **Crew:** see who's done today, send respect, nudge people who haven't started. Crew members appear only as anonymous labels.

Every change comes back with a link that opens the right screen in Daybond.

## Install (Claude Code)

```
/plugin marketplace add Schreezer/holdfast-plugin
/plugin install holdfast@holdfast
```

The plugin adds the Daybond MCP server (`https://holdfast-mcp.chiragmgg.workers.dev/mcp`) and four skills: `holdfast-checkin`, `holdfast-design`, `holdfast-review` and `holdfast-crew`. The server also provides prompts that show up as `/holdfast:checkin`, `/holdfast:new-challenge` and `/holdfast:review`.

Server only, without the skills:

```
claude mcp add --transport http holdfast https://holdfast-mcp.chiragmgg.workers.dev/mcp
```

In Claude on the web or desktop, add a custom connector with the same URL.

## Connecting

1. The first tool call opens a Daybond page with a pairing code and a QR code.
2. Open the link on your iPhone. Daybond shows who's asking; pick an access level and approve with Face ID.
3. Type the 6-digit code Daybond shows into the page. Done.

Only approve a connection you started yourself. Never send anyone the 6-digit code. Disconnect any time in Daybond → Settings → Connected assistants.

## Privacy

Assistants never receive Apple Health numbers, photos, invite codes or your crew's names. See the [privacy policy](https://holdfast-site.chiragmgg.workers.dev/privacy).

## License

MIT
