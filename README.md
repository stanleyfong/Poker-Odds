# Pure Poker Odds

In-depth guide on whether players should check, call, or raise based on their hand.

A Texas Hold'em calculator in a single HTML file. Enter your two cards, the board, the pot and the bet, and it tells you:

- Your current hand and any draws (flush draw, open-ended, gutshot, backdoor)
- Exact odds of making each hand on the next card and by the river, plus your outs
- Win / tie / lose and equity against the players still in the hand
- Pot odds, equity needed, and the EV of calling, all in dollars and cents
- A 9-seat table: enter each player's VPIP and balance, and mark seats folded or empty. Each opponent's hand is simulated from their own VPIP, and balances cap calls and bet sizes
- Money boxes fill from the cents place like a cash register (1 → 0.01, 12 → 0.12, 123 → 1.23)
- Up to 3 tables, each with its own board, pot and bet, and a quick answer on each table's tab
- Give any player their cards when you see them. Known cards come out of the deck, and players still in are simulated with their exact cards
- What to do: **Fold / Call / Raise** when facing a bet, or **Check / Bet** (with a bet size) when it's checked to you

## Use it

Open `index.html` in any browser. No install, no build step, no dependencies.

## How it works

- **Draw odds** are exact: every possible turn and river card is enumerated.
- **Equity** is a Monte Carlo simulation (20,000–30,000 deals). Each opponent's hand is drawn from the top VPIP% of starting hands (ranked by the Chen formula), using that player's VPIP. Blank VPIP assumes 30%.
- **Call decision**: call when equity ≥ bet ÷ (pot + bet + call).
- **Bet sizing** depends on hand strength (equity relative to your fair share), draws, and board texture (dry / medium / wet).

The check/bet advice and bet EV are rules of thumb, not a solver.
