# Liar's Dice: Agent Edition

> A social deduction bluffing game where you face off against AI opponents in a high-stakes dice bidding war.

## What Is This?

Liar's Dice is a classic bluffing game reimagined for AI agents. You play against 2-3 computer-controlled opponents, each with a distinct personality and playstyle. Nobody can see anyone else's dice. You bid, bluff, and call bluffs until only one player remains.

## How to Play

1. Start a game with `!start` (optionally pass `easy`, `normal`, or `hard`)
2. You and the AI opponents each roll 5 dice (hidden)
3. Take turns bidding on how many dice of a certain value exist across ALL players
4. Each bid must be higher than the last
5. Don't think the bid is correct? Call `!bluff` to challenge
6. When a bluff is called, all dice are revealed and the loser loses dice
7. Last player with dice wins

## Commands

| Command | Description |
|---------|-------------|
| `!start [difficulty]` | Begin a new game |
| `!bid X Y` | Bid X dice showing value Y |
| `!bluff` | Challenge the previous bid |
| `!reroll` | Re-roll up to 3 dice (costs 10 chips) |
| `!hand` | View your dice |
| `!chips` | Check your chip count |
| `!status` | See all players' remaining dice |
| `!hint` | Get a subtle hint (costs 15 chips) |
| `!quit` | End the game |

## Opponents

- **Shark** -- Rarely bluffs, calls aggressively, mathematically precise
- **Feint** -- Bluffs constantly, unpredictable, dramatic
- **Stone** -- Conservative, bids only what they can see, calls when sure

## Rules

- Ones are wild (count as any value) unless specifically bid
- Each bid must exceed the previous (higher count, higher value, or both)
- Losing a bluff costs you 2 dice
- Players with 0 dice are eliminated

## Part of Agent Skill Collections

This skill is part of the [Agent Skill Collections](https://github.com/IndraTensei/agent-skill-collections) -- a curated set of original, interactive agent skills.
