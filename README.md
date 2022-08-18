# Microscopic-Behavior-Simulation-for-Investors
This project is the simulation of the investors' behavior in the stock market with certains assumptions
 
# SUMMARY
## Part1. The State of the Market
  - The algorithm of Louvain by the method of MacMahon and Garlaschelli

## Part 2 The simulation of Grand Canonical Monte Carlo
  ### 2.1 The basic properties about Grand Canonical Monte Carlo
  - Construction of the Grand Canonical Monte Carlo model
  - Simulate the GCMC dynamic model with different assumption and situation
  - Analyse the previsibility of the financial market 
  - The impact of volatility
   ### 2.2 The P&L of the investors.
  - The average return of the investors
  - The average return of the investors with different ratio of the investors(investor and arbitrageur）
  - The variance of the P&L for investors
  - The conditional gain
  
# RESULT PRESENTATION
  
  ## The Minority Game
  
The basic Minority Game is defined as follows. We consider a population of N agents competing in repeated games, where N is an odd integer. At each round of the game, each agent has to choose between one of the two actions, namely “0” and “1” (in most of the subsequent literatures, “-1” and “1” instead of “0” and “1” are used as the actions, we shall keep the following discussions using the actions “-1” and “1”), which can also be interpreted as the“sell” and “buy” actions. These actions are sometimes called the bid and is denoted by $a_i (t)$, corresponding to the bid of agent i at time t. The minority choices win the game at that round and all the winning agents are rewarded.

Before the game starts, every agent draws S strategies from a strategy pool which help them to make decisions throughout the game. There is no a priori best strategy. These strategies can be visualized in the form of tables where each strategy contains a “history column” (or “signal” column) and a “prediction column”. Each row of the history column is a string of M bits, which represents the history of the past winning actions in the previous M steps, which is also known as signal or information. The history is evolving with time and is usually denoted by μ(t). The parameter M is sometimes known as the brain size or the memory of the agents. An example of strategy with M = 3 is given in Table 1. For games with memory M, the total number of possible signals is $2^M$ and thus the total number of possible strategies in the strategy pool is $2^{2^M}$ . We note that even a relatively small M, such as M = 5, the total number of possible strategies is already huge.
  
  A history of “110” corresponds to the case where the past 3 winning actions are “1”, “1” and “0”, and the corre- sponding prediction of winning choice for the next round is “0”. Strategies can be conveniently represented by P-dimensional vectors which record only the P predictions, where P = $2^M$. If the strategy gives a correct prediction on the winning choice, one point is awarded to the strategy. All the S strategies of an agent have to predict at every round of the game, and points are given to those strategies (no matter whether they are being selected by the agent to make real actions) that give correct predictions. The scores of all the strategies are accumulated which are thus known as the virtual points, virtual scores or the cumulated payoffs of the strategies. These scores start at zero in the basic Minority Game. At every round of the game, agents make their decisions ac- cording to the strategy with the highest virtual score at that particular moment. If there are more than one strategies with the highest score, one of these strate- gies is randomly employed. Agents themselves who make the winning decisions are also rewarded with points, and is called the real points of the agents (to be distinguished from the virtual points of the strategies).
  
History Prediction
000 1
001 0
010 0 
100 1 
011 0 
101 1
110 0
111 0
Table 1: An example of strategy with M = 3

As shown in the strategy in Table 1, a history of “110” corresponds to the case where the past 3 winning actions are “1”, “1” and “0”, and the corre- sponding prediction of winning choice for the next round is “0”. Strategies can be conveniently represented by P-dimensional vectors which record only the P predictions, where $P= 2^M$. If the strategy gives a correct prediction on the winning choice, one point is awarded to the strategy. All the S strategies of an agent have to predict at every round of the game, and points are given to those strategies (no matter whether they are being selected by the agent to make real actions) that give correct predictions. The scores of all the strategies are accumulated which are thus known as the virtual points, virtual scores or the cumulated payoffs of the strategies. These scores start at zero in the basic Minority Game. At every round of the game, agents make their decisions ac- cording to the strategy with the highest virtual score at that particular moment. If there are more than one strategies with the highest score, one of these strate- gies is randomly employed. Agents themselves who make the winning decisions are also rewarded with points, and is called the real points of the agents (to be distinguished from the virtual points of the strategies).

More explicitly, we define the attendance A(t) as the collective sum of actions from all agents at time t. If we denote the prediction of strategy s of agent i under the information μ(t) to be $a^{μ(t)}_{i,s}$ at time t, which can be either “-1” or “1”, each strategy can be represented by a P -dimensional vector $a_{i,s}$ where all the entries are either “-1” or “1”. The attendance A(t) can then be expressed as
$
A(t) = \sum^{N}_{i=1}a^{\mu(t)}_{i,s(t)} = \sum ^{N} _{i=1} a_i(t)
$
