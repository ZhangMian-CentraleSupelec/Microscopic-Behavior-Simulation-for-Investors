# Microscopic-Behavior-Simulation-for-Investors
This project is based on the  Grand Canonical Monte Carlo model, and from the model we realized the simulation of the investors' behavior in the stock market with certains assumptions
 
 
 ### What we have reached
 
 The increasing of the speculators with in the financial market will reduce their return, while, the fixed strategy investors(producer) will benifit from it.
 
 ![image](https://user-images.githubusercontent.com/110284601/185867792-b980bca7-6b06-49e4-874f-ef7d88594007.png)

 
 
 
 
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
  
  ## The Introduction of Minority Game
  
The basic Minority Game is defined as follows. We consider a population of $N$ agents competing in repeated games, where $N$ is an odd integer. At each round of the game, each agent has to choose between one of the two actions, namely “0” and “1” (in most of the subsequent literatures, “-1” and “1” instead of “0” and “1” are used as the actions, we shall keep the following discussions using the actions “-1” and “1”), which can also be interpreted as the“sell” and “buy” actions. These actions are sometimes called the bid and is denoted by $a_i (t)$, corresponding to the bid of agent $i$ at time $t$. The minority choices win the game at that round and all the winning agents are rewarded.

Before the game starts, every agent draws $S$ strategies from a strategy pool which help them to make decisions throughout the game. There is no a priori best strategy. These strategies can be visualized in the form of tables where each strategy contains a “history column” (or “signal” column) and a “prediction column”. Each row of the history column is a string of $M$ bits, which represents the history of the past winning actions in the previous $M$ steps, which is also known as signal or information. The history is evolving with time and is usually denoted by $\mu(t)$. The parameter M is sometimes known as the brain size or the memory of the agents. An example of strategy with $M = 3$ is given in Table 1. For games with memory M, the total number of possible signals is $2^M$ and thus the total number of possible strategies in the strategy pool is $2^{2^M}$ . We note that even a relatively small M, such as $M = 5$, the total number of possible strategies is already huge.
  
A history of “110” corresponds to the case where the past 3 winning actions are “1”, “1” and “0”, and the corre- sponding prediction of winning choice for the next round is “0”. Strategies can be conveniently represented by $P$-dimensional vectors which record only the $P$ predictions, where $P = $2^M$. If the strategy gives a correct prediction on the winning choice, one point is awarded to the strategy. All the $S$ strategies of an agent have to predict at every round of the game, and points are given to those strategies (no matter whether they are being selected by the agent to make real actions) that give correct predictions. The scores of all the strategies are accumulated which are thus known as the virtual points, virtual scores or the cumulated payoffs of the strategies. These scores start at zero in the basic Minority Game. At every round of the game, agents make their decisions according to the strategy with the highest virtual score at that particular moment. If there are more than one strategies with the highest score, one of these stratgies is randomly employed. Agents themselves who make the winning decisions are also rewarded with points, and is called the real points of the agents (to be distinguished from the virtual points of the strategies).

![image](https://user-images.githubusercontent.com/110284601/185399942-332f36c6-1071-47d8-991b-ad4dad425b78.png)

More explicitly, we define the attendance $A(t)$ as the collective sum of actions from all agents at time $t$. If we denote the prediction of strategy $s$ of agent $i$ under the information $\mu(t)$ to be $a_{i,s}^{\mu(t)}$ at time $t$, which can be either “-1” or “1”, each strategy can be represented by a $P$ -dimensional vector $a_{i,s}$ where all the entries are either “-1” or “1”. The attendance $A(t)$ can then be expressed as

$$\begin{equation}
A(t) = \sum^{N}_{i=1}a^{\mu(t)}_{i,s(t)} = \sum ^{N} _{i=1} a_i(t) 
\end{equation}$$

where $s_{i(t)}$ denotes the best strategy of agent i at time t, i.e

$$\begin{equation}
s_i(t)= argmaxU_{i,s}(t)
\end{equation}$$

and $a_{i(t)} denotes the the real actions or so-called the bids of the agents, i.e.

$$ \begin{equation}
a_i(t)=a^{\mu(t)}_{i,s(t)}
\end{equation} $$

With this A(t), the cumulative virtual score or payoff $U_{i,s}$ of the strategy s of agent i can be updated by

$$ \begin{equation}
U_{i,s}(t+1)=U_{i,s}(t)-sign[a_{i,s}^{\mu(t)}A(t)]
\end{equation} $$

Here one point is added or deducted from the strategies which give a correct or wrong prediction respectively, and is usually called the $step-payoff$ scheme. We note that the negative sign corresponds to the minority nature of the game, i.e. when a $\mu(t)$ and $A(t)$ are of opposite signs, a point is added to the strategy. The real gain of agent $i$ at time $t$ is $−sign[a_i(t)A(t)]$.

Thus, every agent is considered to be adaptive, who can choose between their $s$ strategies and the relative preference of using strategies is changing with time and adaptive to the market outcomes. They are also considered to be inductive, who base their decisions according to the best choice they know, with their limited number of strategies, but not the global best choice given by all possible strategies (the one with highest virtual score among the entire strategy space). The game is also a self-contained model, in which the agents make individual actions according to the history, individual actions are summed up to give the history for the next round which is then used by the agents to make predictions again.

As the total number of agents $N$ in the game is an odd integer, the minority side can always be determined and the number of winners is always less than the number of losers, implying the Minority Game to be a negative sum game. Due to the minority nature of the game and as the two actions are symmetric, the time average of $A(t)$ always has a value of 0 (or $⟨A(t)⟩ = N/2$ if “0” and “1” are employed as actions). Hence, instead of the average attendance, one may be more interested in the fluctuations of attendance around the average values and this turns out to be the one of the most important macroscopic observables in the subsequent development. We denote $\sigma^2$ to be the variance of attendance, or also known as the volatility, given by 

$$\begin{equation}
\sigma^2=⟨A^2⟩-⟨A⟩^2
\end{equation}$$

with $⟨A⟩ = 0$ for games with actions “-1” and “1”. $\sigma^2$ is an inverse measure of the market efficiency in the game. We consider two extreme cases of game outcomes. For the first one, there is only one agent choosing one side while all the others choose the opposite side. There is a single winner and $N − 1$ losers which is considered to be highly inefficient in the sense of resource allocation, and the supply and demand are highly unbalanced. For the second case, $(N − 1)/2$ of the agents choose one side while $(N + 1)/2$ of the agents choose the opposite side. There are $(N − 1)/2$ winners and the supply and demand is maximally balanced. Thus, one may expect to minimize fluctuations of attendance for advantages of agents as a whole.

Some simplifications or modifications to the basic Minority Game are suggested and employed in later literatures, where the major physical features of the models are preserved. A. Cavagna observed that the variance of attendance is almost unaffected if the history string is replaced by a random invented string, provided that all agents receive the same string at the same time. That is, instead of their self-generated winning history, they react to a virtual random information which is completely unrelated to the previous winning groups. In this case, the signal strings are usually called information instead of history. The games which feedback the real history are known as the endogenous games while those games which employ random history is called the exogenous games. In exogenous games, the total number of signal is no longer restricted to be $2^M$ , instead it can be any integer which is usually denoted by $P$ , and is sometimes known as the complexity of information. Every random signal or information appears with a probability of $1/P$. These random informations make the dynamics of the game more stochastic, which is an extreme advantage for analytic approaches. In endogenous game, $P = 2^M$ .

As “-1” and “1” are employed as actions, instead of adding or deducting one virtual point to the strategies, the cumulated payoff $U_{i,s}$ can be updated by the following equation with linear payoff scheme:

$$\begin{equation}
U_{i,s}(t+1)=U_{i,s}(t)-a_{i,s}^{\mu(t)}A(t)
\end{equation}$$

where $A(t)$ is the attendance given by the first equation. A factor of $1/N$, $1/\sqrt{N}$ or $1/P$ are always employed to rescale the last term. While the real gain for agent $i$ is $−a_i(t)A(t)$, the total gain for all the agents is $\sum_i −a_i(t)A(t) = −A^2(t)$, preserving the negative sum nature of the game. This modification is important for analysis while the qualitative behaviours of the game are preserved. It also has the meaning of having a higher reward or larger penalty if a smaller minority or a larger majority group is predicted respectively.

 ## Implementation of Minority Game
 
  ### The price of the stock price with the change of amount of speculators in the market.
  ![image](https://user-images.githubusercontent.com/110284601/185403031-77390c56-9dbe-4d8d-9614-e2e9f7707b8b.png)
  ### The volatility relavant to the number of speculators
  ![image](https://user-images.githubusercontent.com/110284601/185403197-c8e41f9a-d7f9-4649-a70c-8d71de32ccf8.png)
  ### The volatility relavant to the number of producers
  ![image](https://user-images.githubusercontent.com/110284601/185403298-96a60217-6d7c-41a4-b751-0a50c04425af.png)
  ### The volatility relavant to the risk-free return
  ![image](https://user-images.githubusercontent.com/110284601/185403373-277b49f5-875d-478b-b786-8dd8833e26cc.png)

 ## The dynamic of previsibility
 Here we define the provilibility $H$:
 $$\begin{equation}
 $H = \frac{1}{N_sP} E(A|\mu )^2 = \overline{E(A|\mu)^2}$
 \end{equation}$$
 
 ![image](https://user-images.githubusercontent.com/110284601/185403711-e8d27626-39bd-424d-ba85-7274b5d087a2.png)

 ### The condition with volatility explosure
 ![image](https://user-images.githubusercontent.com/110284601/185403798-9ee1b455-24fb-4bbc-9682-7e5e84dcfb47.png)
 
 ### The return for different investors
 ![image](https://user-images.githubusercontent.com/110284601/185403851-0565f221-8653-40bb-9d0a-6efc509d1b5c.png)
 
 ### The average return with the increase of the producers
 ![image](https://user-images.githubusercontent.com/110284601/185404007-8cbb57f0-e3c8-4f89-883c-e9efc8f0bd39.png)

 
