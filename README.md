# Virtual Subdecadence

A browser-based implementation of Virtual Subdecadence, a card game derived from the CCRU (Cybernetic Culture Research Unit) writings. Playable in any browser. Built as a single HTML file with no dependencies.

## The Game

Subdecadence is a variant of the Decadence card game described in CCRU's *Pandemonium* documents. Where standard Decadence uses a truncated playing card deck and pairs summing to ten, Subdecadence replaces this with the 45-card net-span pack corresponding to the Numogram's syzygy structure, and pairs summing to nine.

Virtual Subdecadence is a further abstraction of the game, in which each card's identity is a **net-span** — a descending pair of digits drawn from 0–9, written `X::Y` where X > Y. All 45 possible net-spans constitute the deck.

## Cards

Every card has two numbers:

- **Identity (net-span):** The card's name, e.g. `9::7`, `4::2`, `1::0`
- **Operational number:** `9 − X`, where X is the first digit of the net-span

The operational number is the only value relevant to gameplay. Net-spans are grouped into nine operational phases (op-0 through op-8), with phase sizes descending from 9 cards to 1.

## Rules

1. The 45-card deck is shuffled. Five cards are dealt face-up (**Set-1**) and five face-down (**Set-2**).
2. Set-2 cards are revealed one at a time. Each revealed card automatically pairs with the first available Set-1 card whose operational number sums to 9 with it — a **Syzygy**. If no such card exists, the Set-2 card goes unmatched. The player makes no pairing decisions.
3. A Syzygy scores **+difference** of the two paired operational numbers (op-0 + op-9 scores 9, op-4 + op-5 scores 1).
4. After all five Set-2 cards are revealed, the round resolves.
5. Round score = sum of all syzygy differences − sum of op-numbers of all unmatched Set-2 cards.
6. A positive score banks to the **Angelic Index** and play continues. Zero or negative calls a demon and terminates the Aeon.

## Scoring

| Outcome | Score |
|---|---|
| Syzygy (op numbers sum to 9) | +\|difference of op-numbers\| |
| Unmatched Set-2 card (no syzygy possible) | −op-number |
| Round score = 0 | Lurgo called (Mesh-00), Aeon ends |
| Round score < 0 | Demon called (Mesh = \|score\|, max 44), Aeon ends |

A positive round score is banked to the **Angelic Index** (Aeon total), and play continues. A zero or negative score calls a **demon** and terminates the Aeon.

## The Pandemonium Matrix

A non-positive round score calls a demon from the Pandemonium Matrix — the complete catalogue of 45 Lemurian demons described in the CCRU writings. The demon called corresponds to the mesh-number matching the absolute value of the score (capped at 44). Mesh-00 is **Lurgo**, the Amphidemon of Openings; Mesh-44 is **Ummnu**, the Amphidemon of Earth-Screams.

All demon names, net-spans, types, and epithets are sourced directly from the CCRU's *Pandemonium* document.

## Play

The game is published on itch.io: **[link]**

Or clone this repo and open `index.html` in any browser — no build step, no server required.

```bash
git clone https://github.com/YOURUSERNAME/virtual-subdecadence.git
cd virtual-subdecadence
open index.html
```
