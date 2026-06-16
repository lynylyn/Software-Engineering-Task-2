# Car Comparison Game

## Project Planning
note to self: page 364 of textbook

The aim of this project is to create a 'Top Trumps' card game, using vehicles as the drawable cards. The focus is to provide entertainment, and in order to do this, ensuring the game is fair, logical, and simple. The documentation for this task will be centred around the game's relation to object-oriented programming.

## Part A: Data Selection and Game Attributes
### 6 attributes
1. Horsepower & Max speed
    - This attribute was chosen mainly for its iconic ties to cars, especially in car racing. This attribute being first place increases user entertainment as the speed of a car is simple, numerical, and with a clear 'better' option.
2. Price ($aud)
    - Not dissimilar from the horsepower attribute, the price is another which is easy to rank, and makes it easy to tell when a car is extremely prestigious and high-quality.
3. Distance travelled (km)
    - Both the distance a car has travelled and the age of the car tend to reflect to its overall condition in a numerical way. This attribute was placed third as, although the condition of the car is crucial to its power in the game, the distance travelled will not always necessarily perfectly reflect the condition.
4. Age
    - Almost exactly the same as the attribute listed above, the age of a car often hints towards its condition, whilst also raising other concerns (safety of older models, wear-and-tear with time, etc.). The game dynamics with age are unique, to preserve the importance of vintage cars, a cars ability to 'trump' decreases as it ages until it hits 30 years, then it goes back up again. For example, a car from 1994 would have a rating of 2, and a 1970 car would have a rating of 26. The rating caps at 30 (a 1960 and a 1920 car would both be a '30' for age)
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

## Part E: Interface and Card Design

## Part F: Social, Ethical and Legal Implications
1. **Individual Impact**
    - The game has the ability to influence a player's decision in purchasing a car. It may lead them to believe that a car having high horsepower is the most significant in cars meant for day-to-day driving, which is untrue. Biases towards sports cars, or other high-performing vehicles, may be apparent. The responsibility as a designer to present fair information is important as purchasing cars affects both money and safety of consumers.
2. **Social Impact**
    - The game may appear to discriminate against those with less money as more expensive cars are 'better' in the game dynamics. It also tends to favour sports cars or high-performance cars. The game can be made fairer through the existence of other characteristics which don't necessarily rely on money, such as age, safety, and sustainability.
3. **Environmental Impact**
    - The game has a positive enviornmental impact as it favours cars which are more environmentally friendly (electric cars). It pushes the idea that petrol-fuelled cars are worse than electric cars.
4. **Legal Considerations**
    - Some legal considerations include the use of brand names, logos, and car models for commercial reasons. The use of specific brands could be specifically problematic if advertising includes their trademarked property. When taking data from sites such as carsales.com.au, issues such as reliability should be considered; the cars are user submitted, and listed for the purpose of advertising for profit. This could lead to false information which make the car seem better than it actually is. A warning to users to not use the game as a direction as to what car to buy could ensure users are not mislead.
