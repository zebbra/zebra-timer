# Zebra Timer in Slack

Goal: type a number of minutes, get the ready-made link back — in your own DM, where nobody else sees it.

## Workflow Builder

1. Slack → **Tools → Workflow Builder → New Workflow**
2. Trigger: **From a link in Slack** (it then shows up in the ⚡ menu of the message composer)
3. Step 1: **Send a form**
   - Question: `Minutes`
   - Answer type: **Number**
   - Mark it required
4. Step 2: **Send a message** → recipient **a person** → **yourself**
   - Text:
     ```
     ⏱ {Minutes} min
     https://zebbra.github.io/zebra-timer/?min={Minutes}
     ```
     Insert `{Minutes}` through **Insert a variable** from step 1 — do not type it out.
5. **Publish**, then start it from the ⚡ menu.

The variable is substituted before the message is sent, so it ends up as part of the URL, and Slack links it automatically. Keep the trigger link to yourself and nobody else can run it.

Needs a paid Slack plan. A workflow belongs to whoever built it.

To let a whole room start timers instead, point step 2 at a channel rather than a person.

## Without Workflow Builder

Bookmarks in the DM with yourself, one per duration: open the conversation → **Add a bookmark** → link. Two minutes of setup, no plan features, nothing that can break — but no arbitrary durations.

| Name  | URL                                          |
| ----- | -------------------------------------------- |
| 5min  | https://zebbra.github.io/zebra-timer/?min=5  |
| 10min | https://zebbra.github.io/zebra-timer/?min=10 |
| 15min | https://zebbra.github.io/zebra-timer/?min=15 |
| 20min | https://zebbra.github.io/zebra-timer/?min=20 |
| 30min | https://zebbra.github.io/zebra-timer/?min=30 |
| 45min | https://zebbra.github.io/zebra-timer/?min=45 |
| 60min | https://zebbra.github.io/zebra-timer/?min=60 |
