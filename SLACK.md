# Zebra Timer in Slack

Goal: someone types a number of minutes, Slack posts the ready-made link into the channel.

A real `/slash` command is not possible without a server — Slack sends a POST to an HTTPS endpoint and expects a reply within 3 seconds, and GitHub Pages only serves static GETs. Workflow Builder needs no such endpoint.

## Workflow Builder (no code)

1. Slack → **Tools → Workflow Builder → New Workflow**
2. Trigger: **From a link in Slack** (it then shows up in the ⚡ menu of the message composer)
3. Step 1: **Send a form**
   - Question: `Minutes`
   - Answer type: **Number**
   - Mark it required
4. Step 2: **Send a message to a channel**
   - Channel: whichever you want, or "the channel the workflow was started in"
   - Text:
     ```
     ⏱ Timer running — {Minutes} min
     https://zebbra.github.io/zebra-timer/?min={Minutes}
     ```
     Insert `{Minutes}` through **Insert a variable** from step 1 — do not type it out.
5. **Publish**, then start it in a channel via ⚡.

Slack links the URL automatically; the variable is substituted before posting, so it ends up as part of the URL.

Needs a paid Slack plan. Whoever builds a workflow owns it, so for something meant to outlive the circle, create it from a team account rather than a personal one.

## Fallback: channel bookmarks

No Workflow Builder needed, two minutes of setup: open the channel → **Add a bookmark** → link, one per duration.

| Name  | URL                                          |
| ----- | -------------------------------------------- |
| 5min  | https://zebbra.github.io/zebra-timer/?min=5  |
| 10min | https://zebbra.github.io/zebra-timer/?min=10 |
| 15min | https://zebbra.github.io/zebra-timer/?min=15 |
| 20min | https://zebbra.github.io/zebra-timer/?min=20 |
| 30min | https://zebbra.github.io/zebra-timer/?min=30 |
| 45min | https://zebbra.github.io/zebra-timer/?min=45 |
| 60min | https://zebbra.github.io/zebra-timer/?min=60 |

Arbitrary durations are out with this approach, but there is nothing that can break.
