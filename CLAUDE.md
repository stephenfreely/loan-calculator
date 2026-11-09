# loan-calculator

Single-file static web app. No build, no deps, no package.json, no tests.

- `index.html` — everything (HTML + `<style>` + `<script>`), ~2300 lines.
- Deployed via GitHub Pages from `main` root. Push to `main` = deploy. Live: https://stephenfreely.github.io/loan-calculator/

## Editing

Edit `index.html` directly. Section order: `<style>` (~L7-860), markup (~L860-1425), `<script>` (~L1426-end).

Key JS functions (grep for name, don't read whole file):
- `calc()` — main recompute, driven by input/slider events
- `calcFhbg()` — First Home Guarantee scheme tab
- `calcStampDuty` / `calcNswFhbStampDuty` / `calcNswTransferDuty` — NSW stamp duty rules (rates hardcoded, check against current NSW Revenue rates if asked to update)
- `calcAmortSchedule` / `calcMonthlyPayment` — loan repayment math
- `syncCashInputs` / `updateCashBreakdown` — deposit/price/total-cash reactive sync
- `applyPreset` / `syncPresetButtons` — preset scenario buttons
- `renderBar` / `buildBar` — cash/payment breakdown bar charts
- `switchTab` — results tab switching (Standard structured loan vs First Home Guarantee)

## Workflow

No build/test/lint step exists. Verify changes by opening `index.html` in a browser.

```
git add -A && git commit -m "..." && git push
```
is the full deploy — Pages serves `main` directly.
