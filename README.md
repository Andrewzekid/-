# A Probability Based System for Profit
In Japan, there is a special type of game called Medal Games.
You convert your money into a certain number of medals (e.g: 1000 yen for 1500 medals).
These medals can then be used to play at games such as slot machines or roulettes, akin to a casino (except medals cannot be converted back into real money).
Games that use medals are called <strong>Medal Games</strong>

## Gapori Sushi
One Medal game is Gapori sushi, a roulette like game.
Every round 5 balls are launched into a spinning wheel. 
The spinning wheel has different slots, each slot corresponding to a different type of sushi.
There are a total of 18 slots, and every round the configuration of the slots will reset. Each ball will land on one of the 18 possible slots.

For instance, on 1 round there may be 3 slots for salmon, 4 slots for eggs, 5 slots for nato...etc.
On the next round it will be a totally different configuration: 2 slots for unagis, 4 slots for maguro, 3 slots for kaviar...etc.

At the start of a round, you spend medals betting that a given combination of 2-5 sushis will be chosen.
Of course, the best odds are given by betting that 5 sushis will be chosen. If you get it right, you will win medals.
If you get it wrong, you will lose medals. 

I set out to create a system which, given the current configuration of the wheel, gives you the most profitable combination of 5 sushis to bet on.

## Probability calculations
To make profit, we have to first know the EV (expected value) of all combinations. THis is done firstly by calculating the probability of all combinations.

![images](https://github.com/Andrewzekid/GaporiSushi/assets/79450923/434a47f1-69fe-45a6-aab4-931a16c4780a)

To do this, we run a monte carlo simulation by playing the game 1,000,000 times, noting down the number of occurances for each combination of 5. The number of occurances is then divided by 1,000,000 to find the probability of a specific combination.
After this we calculate the payout for each combination (how much you win if that combination comes up) and find the expected value.

EV = Probability(Win) X Payout - Cost

We then sort all the different combinations by expected values and bet on the combination with the highest EV.

## How to use
* Run all cells in jupyter notebook, stopping after you define the ```calc_optimal_bets()``` function.
* 

## Results
Start: 550 Medals
End (After 10 games): 640 Medals <span style="color:green;">(+90 Medals, ^16%)</span>)

## Video of the Game

<video src="https://github.com/Andrewzekid/GaporiSushi/assets/79450923/015303ac-dbb4-47c9-863b-262bfafe81e1" />
