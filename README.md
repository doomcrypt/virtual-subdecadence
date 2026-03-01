# Virtual Subdecadence

A browser-based implementation of Virtual Subdecadence, a card game derived from the CCRU (Cybernetic Culture Research Unit) writings. Playable in any browser. Built as a single HTML file with no dependencies.

---

## The Game

Subdecadence is a variant of the Decadence card game described in CCRU's *Pandemonium* documents. Where standard Decadence uses a truncated playing card deck and pairs summing to ten, Subdecadence replaces this with the 45-card net-span pack corresponding to the Numogram's syzygy structure, and pairs summing to nine.

Virtual Subdecadence is a further abstraction of the game, in which each card's identity is a **net-span** — a descending pair of digits drawn from 0–9, written `X::Y` where X > Y. All 45 possible net-spans constitute the deck.

---

## Cards

Every card has two numbers:

- **Identity (net-span):** The card's name, e.g. `9::7`, `4::2`, `1::0`
- **Operational number:** `9 − X`, where X is the first digit of the net-span

The operational number is the only value relevant to gameplay. Net-spans are grouped into nine operational phases (op-0 through op-8), with phase sizes descending from 9 cards to 1.

---

## Rules

1. The 45-card deck is shuffled. Five cards are dealt face-up (**Set-1**) and five face-down (**Set-2**).
2. Set-2 cards are revealed one at a time. Each time a card is revealed, the player selects a Set-1 card to pair with it.
3. A valid pair — called a **Syzygy** — is one where the two cards' operational numbers sum to 9. The pair scores **+difference** of their operational numbers (so op-0 + op-9 scores 9, op-4 + op-5 scores 1).
4. An invalid pair scores **−sum** of the operational numbers.
5. All five Set-2 cards must be paired before the round resolves. Any Set-1 cards left unpaired at the end score **−op-number**.
6. A round (an **Aeon**) ends when the total score is zero or negative. Positive scores accumulate across rounds until termination.

---

## Scoring

| Outcome | Score |
|---|---|
| Syzygy (op numbers sum to 9) | +\|difference\| |
| Failed pair (op numbers don't sum to 9) | −sum |
| Unpaired Set-1 card at round end | −op-number |

A positive round score is banked to the **Angelic Index** (Aeon total) and play continues. A zero or negative score calls a **demon** and terminates the Aeon.

---

## The Pandemonium Matrix

A non-positive round score calls a demon from the Pandemonium Matrix — the complete catalogue of 45 Lemurian demons described in the CCRU writings. The demon called corresponds to the mesh-number matching the absolute value of the score (capped at 44). Mesh-00 is **Lurgo**, the Amphidemon of Openings; Mesh-44 is **Ummnu**, the Amphidemon of Earth-Screams.

All demon names, net-spans, types, and epithets are sourced directly from the CCRU's *Pandemonium* document.

---

## Play

The game is published on itch.io: **[link]**

Or clone this repo and open `index.html` in any browser — no build step, no server required.

```bash
git clone https://github.com/YOURUSERNAME/virtual-subdecadence.git
cd virtual-subdecadence
open index.html
```

---

## Sources

- CCRU, *Pandemonium* — `ccru.net/digithype/pandemonium.htm`
- CCRU, *Numogram* writings and video elaborations of Subdecadence rules
- CCRU, *Abstract Culture* / *Digital Hyperstition* zine series

---

## License

This is a fan implementation of a game described in publicly available CCRU texts. No commercial use. All demon names, the Numogram, and the Pandemonium Matrix are CCRU.
