# Car Comparison Game

## Project Planning
note to self: page 364 of textbook

The aim of this project is to create a 'Top Trumps' card game, using vehicles as the drawable cards. The focus is to provide entertainment, and in order to do this, ensuring the game is fair, logical, and simple. The documentation for this task will be centred around the game's relation to object-oriented programming.

## Part A: Data Selection and Game Attributes
### 6 attributes
1. Horsepower & Max speed
    - This attribute was chosen mainly for its iconic ties to cars, especially in car racing. This attribute being first place increases user entertainment as the speed of a car is simple, numerical, and with a clear 'better' option.
2. Price ($aud)
    - Not dissimilar from the horsepower attribute, the price is another which is easy to rank, and excellently compliments the other attributes as, for example, a car with a low price and a high horsepower is much better than one a car with a high price and low horsepower.
3. Distance travelled (km)
    - Both the distance a car has travelled and the age of the car tend to reflect to its overall condition in a numerical way. This attribute was placed third as, although the condition of the car is crucial to its power in the game, the distance travelled will not always necessarily perfectly reflect the condition.
4. Age
    - Almost exactly the same as the attribute listed above, the age of a car often hints towards its condition, whilst also raising other concerns (safety of older models, wear-and-tear with time, etc.). This attribute was placed below distance travelled as it is possible to keep a car in good condition over a long period of time with low use.
5. Safety rating
    - The safety rating, while being a crucial factor when purchasing a car, is not necessarily an impactful attribute to the game as it doesn't induce the same enthusiasm as speed or brand may.
6. Sustainability (petrol-hybrid-electric / 123)
    - Sustainability has beeen placed last in power for a few reasons. Its reason for inclusion is the importance of sustainability in our current society; however, in the game's dynamics, there are limited options for how sustainable a car can be (only three) and thus it would be difficult to compare exact numbers.

Fairness within a board game is generally described to mean that all players have equal opportunities and chances to win the game. This edition of 'Top Trumps' ensures that fairness through random draws of a card, the same amount of turns for each player, and ease of understanding regardless of experience. Fairness in a project like this is important as it fosters positive experiences for the players, encourages healthy competition, and maintains the game's integrity.

## Part B: Class Design
| Car |
| - |
| Horsepower and Max Speed: integer |
| Price: float |
| Distance Travelled: float |
| Age: float |
| Safety Rating: integer |
| Sustainability: string |
| ---------------------------------------- |
| compare() |

The car class is the most important of the system. It is on the card, and holds each attribute that makes a card more or less powerful.

| Card |
| - |
| Colour: string |
| ---------------|
| draw()|

The card class is mostly used to hold the car, with its only attribute being its colour.

| Deck |
| - |
| No. of cards left: integer |
| --------------------------
| shuffle() |

The deck holds every card which isn't held by a player. Its ability to be shuffled is its most important feature.

| Player |
| - |
| No. of turns left: integer |
| Wins: integer |
| --------------------------- |
| play() |
| forfeit() |

The player possesses the cards and is able to interact with the entire game/system.

| Game |
| - |
| Cards available: integer |
| Number of players: integer |
| --------------------------- |
| display_rules() |
| deal() |

The game is the superclass. All classes other than the player are included.

## Part C: Class Diagram

![Class Diagram](<Class Diagram.jpg>)

Note that the number of players attribute for the game class was not included. The player should also have zero to many (0..*) cards, according to the game mechanics below.

## Part D: Game Mechanics Design
- At the beginning of the game, the deck is shuffled and divided up evenly among the players. The player to the dealer's left goes first, and selects a category from their card. The other players reveal what number they had for that category. The player with the highest number keeps all other cards from that round. The game continues until one player has all cards or all other players have forfeited.

- In the case of a draw, the players must compare the next category on the card.

- One possible way the game could be unfair or not function as intended is through the 'sustainability' category which only has three options. This issue is rectified through the ability to move on to the next category if there's a draw (e.g., if three players have electric cars, they could compare horsepower and max speed instead).

![Structure Chart](<Structure Chart.jpg>)