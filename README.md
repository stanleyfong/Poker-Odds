# Pure Poker Odds

A Texas Hold'em calculator in a single HTML file. Enter your two cards, the board, the pot and the bet, and it tells you:

- Your current hand and any draws (flush draw, open-ended, gutshot, backdoor)
- Exact odds of making each hand on the next card and by the river, plus your outs
- Win / tie / lose and equity against 1–9 opponents (simulated, with an adjustable opponent hand range)
- Pot odds, equity needed, and the EV of calling, all in dollars and cents
- Up to 3 tables, each with its own board, pot and bet, and a quick answer on each table's tab
- Several hands per table sharing one board. Cards in your other hands are removed from the deck, so outs and odds account for them
- What to do: **Fold / Call / Raise** when facing a bet, or **Check / Bet** (with a bet size) when it's checked to you

## Use it

Open `index.html` in any browser. No install, no build step, no dependencies.

## How it works

- **Draw odds** are exact: every possible turn and river card is enumerated.
- **Equity** is a Monte Carlo simulation (20,000–30,000 deals). Opponent hands are drawn from the range you pick (any two cards, or the top 50/30/15% ranked by the Chen formula).
- **Call decision**: call when equity ≥ bet ÷ (pot + bet + call).
- **Bet sizing** depends on hand strength (equity relative to your fair share), draws, and board texture (dry / medium / wet).

The check/bet advice and bet EV are rules of thumb, not a solver.
