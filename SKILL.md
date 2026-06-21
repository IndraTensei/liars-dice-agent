---
name: liars-dice-agent
description: A social deduction bluffing dice game. Challenge AI opponents in bidding wars, call bluffs, and outlast the table.
version: 1.0.0
license: MIT
metadata:
  hermes:
    tags: [Game, Bluffing, Social Deduction, Dice]
---

# Liar's Dice: Agent Edition

## When to Use
Load this skill when the user wants to play a bluffing/deduction game, specifically a dice bidding game against AI opponents.

## Overview
A social deduction game where the player faces 2-3 AI opponents in a dice bidding war. Each player rolls in secret. Players bid on the total pool. Bluff, deduce, and outlast everyone. Last player with dice wins.

## Quick Reference

| Command | Action |
|---------|--------|
| `!start [easy/normal/hard]` | Begin new game |
| `!bid X Y` | Bid X dice of value Y |
| `!bluff` | Call previous bid |
| `!reroll` | Re-roll up to 3 dice (-10 chips) |
| `!hand` | View your dice |
| `!chips` | Check chip count |
| `!status` | All players' dice remaining |
| `!hint` | Get a nudge (-15 chips) |
| `!quit` | End game |

## Procedure

### 1. Setup
- Agent acts as Game Master + controls 2-3 AI opponents
- Each player: 5 dice, 100 chips
- Roll all dice, keep hidden

### 2. Bidding Phase
- Players bid clockwise: "X value-Y" = at least X dice showing Y across ALL players
- Each bid must exceed previous (higher count, higher value, or both)
- Ones are wild unless specifically bid
- Players may pass

### 3. Bluff Resolution
- When `!bluff` is called, reveal all dice
- Bid was correct or under: bidder wins, caller loses 2 dice
- Bid was over: caller wins, bidder loses 2 dice
- Zero dice = eliminated

### 4. Win Condition
- Last player standing wins

### AI Opponents
- **Shark**: Rarely bluffs, aggressive caller, mathematical
- **Feint**: Constant bluffer, unpredictable, dramatic
- **Stone**: Conservative, bids only what they see, calls when sure

## Difficulty
- **Easy**: 2 opponents, obvious mistakes, generous hints
- **Normal**: 3 opponents, balanced play
- **Hard**: 3 opponents, near-optimal, no hints

## Scoring
- Win round: +50 chips per eliminated opponent
- Correct bluff call: +20 chips
- Survive bluff: +10 chips

## Pitfalls
- Never reveal hidden dice unless bluff is called
- Enforce bidding rules strictly — no invalid bids
- AI must not act on information it shouldn't have
- Keep pace — if user stalls, AI makes decisions
- Game must be winnable even on hard

## Verification
- Confirm game ends with a winner
- Chip counts and dice counts stay consistent
- All eliminations are correctly tracked
