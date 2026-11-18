# Schema

All tables are UTF-8 CSV with a Parquet twin. Join on `slot_slug` → `slots.slug` and
`provider_slug` → `providers.slug`. Lists inside a cell are pipe-separated slugs.

## slots

one row per game: identity, maths, grid, mechanics, themes, features, bonus economics, capture date

- `slug` — stable id, also the page slug on i-gaming.tools
- `provider_ref` — the provider's own internal game code (what integrations use)
- `rtp_default` — RTP of the default configuration, %
- `rtp_variants_count / rtp_min / rtp_max` — how many RTP configurations exist and their range
- `max_win_x` — max win as a multiple of the bet
- `min_bet / max_bet` — bet limits seen in the demo, demo currency
- `bonus_buy_cost_x / ante_bet_cost` — costs in multiples of the bet
- `jackpot_tiers` — JSON list of tiers when the game has a jackpot
- `themes / features` — pipe-separated slugs from the themes / features tables
- `coverage_gap_count` — number of items we could not capture for this game
- `captured_at` — when the official demo was captured
- `capture_method` — always: live demo capture in a headless browser, values verified with OCR
- `demo_url / source_url` — embeddable demo and the game page on i-gaming.tools

## rtp_variants

one row per RTP configuration a game ships with, and the condition when stated

## bonus_buys

bonus buy options with their cost in bets

## accessibility

per-game accessibility notes: colour-blind, hearing and other groups

## coverage_gaps

what was and was not captured for each game, so gaps are explicit, not guessed

## providers

studio profile: HQ, offices, founding year where known, RTP spread, releases by year

## licences

provider licences with regulator and licence number, across jurisdictions

## themes

theme taxonomy with aliases (entity resolution layer)

## features

feature taxonomy with aliases
