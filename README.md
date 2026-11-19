# J.A.R.V.I.S. Mission Control

A single-page, Iron Man style HUD dashboard. Everything lives in `index.html` (all CSS and JS inline, no dependencies).

## Run

Open `index.html` in Chrome or Edge. Voice input uses the browser's speech recognition, which needs an internet connection.

- Click the central core or hold **Space** to talk
- Type commands in the bottom bar (e.g. `progress`, `eta`, `status`, `recommendations`)
- **MORNING BRIEF** reads a spoken briefing plus the top 3 recommendations for the day

## Wiring real data

Every number comes from the `DATA` object at the top of the script. Set `DATA.settings.simulate = false` once you connect real sources, then update values at runtime with:

```js
JARVIS.setObjective(70000);
JARVIS.setStat("REVENUE MTD", 70000);
JARVIS.setVital("CPU CORE", 55);
JARVIS.refresh();
```

For open-ended answers, replace `getAssistantReply(text)` with a call to your own LLM/backend. It must return a string.
