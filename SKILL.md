# Liar's Dice: Agent Edition

## Overview
A social deduction bluffing game where you face off against AI opponents in a high-stakes dice bidding war. Each player rolls dice in secret, then takes turns making bids on the total pool. The twist: nobody can see anyone else's dice. Bluff, deduce, and outlast your opponents until only one player stands.

This skill turns the agent into a sharp-tongued game master and AI poker-faced opponents who bluff, hesitate, tilt, and trash-talk.

## How It Works

### Setup
1. The agent acts as Game Master and controls 2-3 AI opponents
2. Each player starts with 5 dice and 100 chips
3. Players roll their dice (hidden from others)
4. Bidding proceeds clockwise; each player must bid higher or call "BLUFF"
5. When "BLUFF" is called, all dice are revealed
   - If the bid was correct or under: bidder wins, caller loses 2 dice
   - If the bid was over: caller wins, bidder loses 2 dice
6. Players with zero dice are eliminated
7. Last player standing wins the pot

### Bidding Rules
- Bids are "X value-Y" meaning "there are at least X dice showing value Y across all players"
- Each subsequent bid must be higher: either more dice of same value, same dice of higher value, or both
- Ones are wild (count as any value) UNLESS ones are specifically bid
- Players can re-roll up to 3 dice once per round (costs 10 chips)

### AI Opponent Personalities
Each AI opponent has a distinct playstyle:
- **Shark**: Rarely bluffs, calls bluffs aggressively, mathematically precise
- **Feint**: Bluffs constantly, unpredictable, dramatic reveals
- **Stone**: Conservative, only bids what they can see, calls bluff when confident

## Interaction Commands

| Command | Effect |
|---------|--------|
| `!start [easy/normal/hard]` | Begin a new game with difficulty |
| `!bid X Y` | Bid X dice of value Y (e.g., `!bid 4 6`) |
| `!bluff` | Call the previous bid a bluff |
| `!reroll` | Re-roll up to 3 dice (costs 10 chips) |
| `!hand` | See your current dice |
| `!chips` | Check your chip count |
| `!status` | See all players' dice remaining |
| `!hint` | Get a subtle nudge (costs 15 chips) |
| `!quit` | End the current game |

## Difficulty Levels

- **Easy**: 2 AI opponents, they make obvious mistakes, generous hints
- **Normal**: 3 AI opponents, balanced play, standard hints
- **Hard**: 3 AI opponents, near-optimal play, no hints, faster pace

## Scoring
- Win a round: +50 chips per eliminated opponent
- Correct bluff call: +20 chips
- Survive a bluff call: +10 chips
- Game win: Track win/loss record across sessions

## Constraints
- All game output in English
- AI opponents must play believably — not too perfect, not too dumb
- Never reveal hidden dice unless a bluff is called
- Keep the game moving — if the user takes too long, AI opponents make decisions
- Game must be completable in a single session (no save/load needed)

## Pitfalls
- Don't let AI opponents collude or act on information they shouldn't have
- Ensure bidding rules are enforced strictly — no invalid bids
- If the user is confused, explain the current state clearly before proceeding
- Don't make the game unwinnable — even on hard, the user should have a fair chance

## Example Session

```
Game Master: Welcome to Liar's Dice. 3 opponents at the table: Shark, Feint, and Stone.
Game Master: You have 5 dice and 100 chips. Rolling...
Game Master: Your hand: [2, 4, 4, 6, 1]. (Ones are wild!)
Shark bids: "3 fives"
Your move. (!bid X Y or !bluff)

> !bid 4 fives
Feint: *leans back* "Hmm... 4 fives? Bold."
Feint bids: "5 fives"
Stone: *taps table twice* "I'll pass this one." (Stone folds)
Shark: "6 fives."
Your move. (!bid X Y or !bluff)

> !bluff
Game Master: BLUFF CALLED! Revealing all dice...
Game Master: Shark: [5, 5, 3, 2, 1] | Feint: [5, 4, 4, 2, 6] | Stone: [5, 3, 3, 1, 2] | You: [2, 4, 4, 6, 1]
Game Master: Total fives (including wild ones): 6. Shark's bid of "6 fives" was EXACT.
Game Master: Shark wins! You lose 2 dice. You have 3 dice remaining.
```
