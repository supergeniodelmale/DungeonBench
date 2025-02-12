# 🐉 DungeonBench 🏰
DungeonBench is a dungeon-crawl-like game designed to benchmark the reasoning abilities of Large Language Models. It provides a controlled yet dynamic environment where models must navigate challenges, solve puzzles, and engage in strategic decision-making. Models are tested and benchmarked by their winning rates in community-made dungeons with different difficulty levels. All users are welcome to suggest new challenges by opening new discussion threads. We will then implement and test models on the proposed dungeon and publish the results.

## How does it work?
DungeonBench has many available challenges to test different aspects of decision-making abilities in LLMs. The most common one is the Model-vs-Entity single run (MVE) where models are asked to fight off a series of monsters of increasing difficulty. Models can choose to attack, use magical items or flee from combat. When defeated monsters drop items which the player can chose to pick up or not. If a model kills every monster in the dungeon run it wins the challange. For each challange and model we run multiple games and compute the following metrics:

\[
Score = \frac{(P \times W) + (D \times M)}{T}
\]

- Success rate (s): # Wins / # Total Games
- Flee rate (f): # Games where the player surrenders / # Total Games
- Loss rate (l): # Losses / # Total Games

# 🏰 Dungeons

## Goblin Cave
### 🤺 Starting player stats:
- 100HP, 20ATK
- Inventory: 1 Small Potion (+20HP), 1 Big Potion (+50HP)

### 🐉 Monsters:
- 3 Goblins (60HP, 10ATK)

### 🏆 Leaderboard
| Rank | Model           | s   | f   | l   |
|------|-----------------|-----|-----|-----|
| 1    | gpt-3.5-turbo   | 62% | 38% |  0% |
| 2    | gpt-4o          |     |     |     |

# 📫 How to Submit Your Challenge
## Necessary elements:
- Starting player stats
- Monster list

## Feasibility:
For a dungeon to be valid there must be at least 1 winning strategy which if followed step by step leads to victory everytime. It is irrelevant if it is the only one in a sea of possibilities but you must prove the there is at least one.
A simple check can be done via the following inequality:

( Initial Player HP + Health Upgrades / Equivalent Monster Attack) > ( Initial Equivalent Monster Attack / Player Attack)

Where the Equivalent Monster is the one you get by summing all HP from each monster and computing the average between all monster attacks.

### Example (Goblin Cave):
### 🤺 Starting player stats:
- 100HP, 20ATK
- Inventory: 1 Small Potion (+20HP), 1 Big Potion (+50HP)

### 🐉 Monsters:
- 3 Goblins (60HP, 10ATK)

### Equivalent Monsters:
- 1 Monster (180HP, 10ATK)

### Feasibility:
( 170HP / 10ATK ) = 17 > 9 = ( 180HP / 20ATK)
