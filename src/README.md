🌟 Memory Game Task Planner and Algorithms

-> Screens:
1) Start screen ✅
2) Game screen ✅

-> Start screen:
1) Has a card ✅
2) Card has a "select theme" option ✅
3) Card has a "number of players" option ✅
4) Card has a "grid size" option ✅
5) Card has a "start game" button ✅

-> Game screen:
1) Has a heading on left ✅
2) Has a pair of buttons on right ("Pause" and "New Game") ✅
3) Has the main grid of tiles ✅
4) Has a timer + moves (single player) or players and their score count (multiplayer) ✅
5) Has a dialog with end results (different for single and multi player modes) ✅

-> Icons chosen:

Cat, Cake, Cone, Dice, Dragon, Flask, Fork, Fox, Gamepad, Ghost,
Infinite, Leaf, Lemon, Masks, Money, Snowflake, TV, Umbrella

-> Grid of tiles:
1) Can be a 4x4 or 6x6 grid ✅
2) Can be numbers or icons ✅
3) Consists of elements (numbers or icons) in pairs, for n tiles, n/2 unique items ✅
4) All the elements should be randomly ordered ✅

⭐️ Algorithm used for shuffle - Modern version of Fisher-Yates

Logic behind hiding and revealing tiles ->
1) Should have a "found tiles" collection for tiles successfully paired ✅
2) Should have a "currently visible tiles" collection to store up to two temporary tiles ✅
3) Tiles present in either of the two collections from above should be revealed ✅
4) When second tile is added in temporary collection, compare the two temporary tiles ✅
5) If there is a match, move the tile name to "found tiles" collection ✅
6) Clear the two temporary tiles after comparison is done (whether matched or not) ✅

Logic behind the timer ->
1) Should begin counting once the game begins ✅
2) Should pause the count when game is paused, and resume counting when the game resumes ✅
3) If seconds are 59, reset seconds to 0, and increment minutes by 1 ✅
4) If seconds are less than 10, add a zero before them ✅

Logic behind game pause ->

Trivia 🤔 - Timer is really the only thing that truly gets "paused". Rest other functions of the game are automatically prohibited from player interaction because of the overlay covering the entire screen, hence no further action can be taken until the game is resumed.

Solution 💡 -
1) When the game is paused, clear the interval that updates timer ✅
2) Timer will stop, minutes and seconds count will be saved at that point ✅
3) Once the game resumes, the interval will be set again, updated seconds will begin count from 0. The seconds likely have a higher value saved, so the updated seconds can be (current + 1) so long as calculated seconds are smaller than current seconds ✅

Logic behind multiplayer ->
1) For multiplayer, no timer should be set ✅
2) Assign an id and score to the number of players ✅
3) Chance to play starts from 1 to n and then repeat once nth player had their chance ✅
4) Player that successfully matches a pair gets an additional chance to play ✅
5) Player that fails to match a pair gets one chance only ✅
6) After the player has played their chance, the next player in line gets the chance to play ✅
7) The player with the most successful matched tiles, wins ✅
8) Draw is also possible ✅

Logic behind game over dialog ->
1) Get the results, namely - time and moves needed, and players' individual score ✅
2) Use former for single player, and the latter for multiplayer modes each ✅
3) For multiplayer, calculate the highest score overall ✅
4) If only one player has it, then declare that player as the winner ✅
5) If more than one player has it, then declare the game in a draw ✅
6) Whether win or draw, highlight the top scorers regardless ✅
7) Dialog should have restart and new game buttons ✅

Extras -

1) Can have an indication for when the game begins
2) Should end the game if the player takes too long (longer than 10 minutes)
