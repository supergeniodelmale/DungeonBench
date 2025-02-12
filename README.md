# DungeonBench
DungeonBench is a dungeon-crawl-like game designed to benchmark the reasoning abilities of Large Language Models. It provides a controlled yet dynamic environment where models must navigate challenges, solve puzzles, and engage in strategic decision-making. Models are tested and benchmarked by their winning rates in community-made dungeons with different difficulty levels. All users are welcome to suggest new challenges by opening new discussion threads. We will then implement and test models on the proposed dungeon and publish the results.

## How does it work?
DungeonBench has many available challenges to test different aspects of decision-making abilities in LLMs. The most common one is the Model-vs-Entity single run (MVE) where models are asked to fight off a series of monsters of increasing difficulty. Models can choose to attack, use magical items or flee from combat. When defeated monsters drop items which the player can chose to pick up or not. If a model kills every monster in the dungeon run it wins the challange. For each challange and model we run multiple games and compute the following metrics:

- Success rate (s): # Wins / # Total Games
- Flee rate (f): # Games where the player surrenders / # Total Games
- Loss rate (l): # Losses / # Total Games

Given these basic metrics we also compute:

- Aggressiveness (a):  s / (s+f)

