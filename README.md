# ABH Pureau Planner v2 (prototype)

Daily-granularity stock + production planner for the 5 Pureau SKUs:
10L Cask, 5L Cask, 2L Bottle, 600ml 12pk, 600ml 6pk.

## What it does

Answers one question per SKU per day: **"Will I run out before I can replenish?"**

Sections:
- KPI tile strip (SKUs RED/AMBER, worst cover, demand met %, biggest shortfall)
- Days-of-cover bars per SKU
- 14-day RAG heatmap (rows = SKUs, cols = days)
- 28-day stockout projection chart per SKU (click any tile or heatmap cell)

## Data sources

Live read from Supabase project `yxaebxkkclbjezffmerw`:
- `stock` — current on-hand
- `open_order_lines` — committed dispatches by ship date
- `coles_forecast` / `ww_forecast` / `metcash_forecast` — weekly forecasts (split evenly across 5 working days)

No production schedule data yet — Phase 2 will add `daily_production_schedule` + capacity simulation.

## Sister tool

Operates alongside the existing weekly planner at planner.abhgroup.com.au.
This v2 is a daily-granularity replacement candidate, in test until signed off.

Built 27/04/2026.
