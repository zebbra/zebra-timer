# Zebra Timer

A workshop countdown. The screen fills with red grass; a zebra grazes its way through it. Time left is the red area still standing — readable from the back of the room without reading the clock.

**Live:** https://zebbra.github.io/zebra-timer/

Single file, no dependencies, no build step.

## Starting straight from a link

`?min=<number>` starts the countdown the moment the page opens. Valid range is 1–240; anything else falls back to the picker.

```
https://zebbra.github.io/zebra-timer/?min=12
```

It works the other way round too: any timer you start by hand writes its duration into the address bar, so copying the URL is enough to share it.

> **Sound:** A timer opened from a link has seen no user interaction yet, so browsers keep the audio context suspended. The end chime only fires once somebody has clicked into the window or pressed a key. The visual end signal (full-screen flash) is unaffected.

## Controls

| Input               | Effect                         |
| ------------------- | ------------------------------ |
| Click a preset      | start 1–60 minutes             |
| Number + Enter      | any duration (1–240 min)       |
| Tap/click the field | pause / resume                 |
| `Space`             | pause / resume                 |
| `R`                 | restart with the same duration |
| `F`                 | fullscreen (for a projector)   |
| `Esc`               | back to the picker             |

On a touch device the keyboard hints turn into real buttons and the presets get thumb-sized targets. Fullscreen only appears where the browser actually has the API — it shows on Android, and is hidden on iOS Safari, which has none for pages.

## Granularity

One tuft is one minute, as long as that lands between 24 and 60 tufts. Shorter timers step down to 30/15/10/5 seconds, longer ones up to 2/5 minutes. The caption in the bottom left always says what a tuft is currently worth.

<details>
<summary>Why not always one tuft per minute</summary>

Five minutes would be five tufts — the meadow looks empty and the grazing jumps. Three hours would be 180, which nobody can read. Holding the count between 24 and 60 keeps both ends usable without making the unit awkward.
</details>

## Slack

Workflow Builder, no code required — see [`SLACK.md`](SLACK.md).

## Development

`?speed=60` runs the clock 60× faster, so a 12-minute timer is done in 12 seconds. Combine them: `?min=12&speed=60`.

Colours, zebra stripes and grass blades all use the same stroke as the zebbra logomark: 45°, round caps, varying lengths, some broken into segments. Brand red is `#ff2235`.
