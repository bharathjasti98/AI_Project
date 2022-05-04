Project name: Sum_It_up 

Project Statement:

The goal of the game "Sum It Up" is to be the first player to reach 100 points. 
Each player's turn consists of repeatedly rolling a die. 
After each roll, the player is faced with two choices: roll again, or hold (fall off to roll again).
If the player rolls a 1, the player scores nothing and it becomes the opponent's turn.
If the player rolls a number other than 1, the number is added to the player's turn total and the player's turn continues.
If the player holds, the turn total, the sum of the rolls during the turn, is added to the player's score, and it becomes the opponent's turn.
For such a simple dice game, one might expect a simple optimal strategy. As we shall see, 
this simple dice game yields a much more complex and captivating optimal policy.

Approach:

Multi agent Q – learning, to make the agents learn on the past results stored which were played by themselves.
We will use the basic analysis to define how to play optimally and when the turn score is less than the risk factor of losing all, bot continue to roll the dice.
First of all, bot follows simple tactics to win the game. 
In extreme conditions where winning chances decreases with simple tactics, check probability of winning of bot and human and takes the decision. 
We use value iterating by computing which action to take in each state to maximize rewards. 

Deliverables:

A fully developed "sum it up" game using AI where a bot can use all the strategies we calculated and plays against a human.
Bot can take decisions based on simple tactics, on the probability of winning the game and value iterating algorithm.

Evaluation:

Games are very effective to take decisions. "Sum it up" is a game where we have a good of scope for taking optimal decisions to win a game.
As part of initial phase, we develop a python program to play Sum it up Game without any strategies behind.
We continue to develop the code such that bot can play to win using simple strategies.
Next, We use maximum probability to win a game strategies and implement in the game.
Finally, We use value iteration, to get optimal solution to the bot.
In this game, sum it up we can play with fully trained automated bot.

Project Description:

Intially, we are defining two Players
There are three strategies:

1) strategy='learn' - learn, i.e. make future decisions based on past decisions; parameter: learn_from, a list of sources to learn from
2) strategy='hold' - hold at a specified integer; parameter: hold_at
3) strategy='random' - decide randomly whether or not to hold; parameter: hold_p

Consider the following example.

Player 1:
a = Player(name='Teja', write_to='A_demo_dec', strategy = 'learn', learn_from=['A_demo_dec', 'B_demo_dec'])
Player: Teja
Data written to: A_demo_dec
Strategy: Learn from the following sources.
 A_demo_dec B_demo_dec
 
Player 2:
b = Player(name='Bharath', write_to='B_demo_dec', strategy = 'random', hold_p=1)
Player: Bharath
Data written to: B_demo_dec
Strategy: Random with probability 1.0.
Tournament
A tournament is a sequence of games. It is initialised as follows.

t = Tournament(a, b)
We first delete old player data, so that Venkata Teja starts learning from scratch and we can see the improvement over the course of the tournament.

Running play_games() will simulate n (default 100) games. Here, all decisions and whether or not the lead to victory are recorded after each game, and Teja will base future decisions on that experience.

t.play_games(n=10)
Teja (5 wins) : (5 wins) Bharath
Here teja won 5 matches and Bharath also won 5 matches.

t.play_games(n=190)
Teja (73 % wins) : (27 % wins) Bharath
Here Teja (Bot) won 146 matches and Bharath won 54 matches.

t.play_games(n=800)
Teja (95 % wins) : (5 % wins) Bharath
Here Teja (Bot) won 950 matches and Bharath won 50 matches.

Here we can see teja bot won 95 percent of the entire matches. 

The learning algorithm:

The undertaking to be learned is to choose whether to proceed with a go or to hold. 
The choice relies just upon the player's score, the adversary's score, and the ongoing turn all out (cf. the Wiki page). This gives a little boundary space for the capacity that goes with the choice - - its size is . 
Subsequently, rather than utilizing AI calculations, the choices that have been made in a game are kept in a grid once the game is finished up. 
This occurs by just expanding counters, and it enjoys the benefit that the space intricacy for the calculation is consistent. The lattice is of size .
If in a resulting game, Teja needs to go with a choice for a specific circumstance own_score, opp_score, turn_total (initial three dimesions), then the comparing framework (last two aspects) shows her how frequently proceed/hold choices have lead to wins/misfortunes previously. 
She can then pursue her choice in light of that.

t.play_game()
Play game is a function where entire game will execute and we can see the results, where bot playing well than the random player.

 




