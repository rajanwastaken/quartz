---
title: "Evolutionary Game Theory"
date: 2022-10-19
tags:
- work
- research
---

Biological and organ structures exist as a network of complex behaviours within populations. This raises questions as to how we can model the interconnectedness of human organisms and functions.

![[images/Pasted image 20221203214336.png]]

Evolutionary game theory is a branch of game theory that offers a unique perspective to this field of inquiry. At its core, evolutionary game theory is concerned with how individual behaviors and strategies can change over time in response to the actions of others. It is based on the assumption that individuals will tend to adopt strategies that are successful in achieving their goals, and that these strategies will evolve over time as individuals compete with each other for resources. This process can lead to the emergence of complex behavior, such as cooperation and coordination, as well as the formation of social structures and hierarchies.

This concept can be used to understand how different organs within the human body may evolve in response to the strategies of other organs. The heart and lungs may be seen as using an evolutionarily stable strategy in order to maintain a consistent supply of oxygen to the body's cells. This strategy may be invaded by other organs, such as the liver or kidneys, if they are not functioning properly.

# Organ Networks

The heart and lungs may be seen as using an evolutionarily stable strategy in order to maintain a consistent supply of oxygen to the body's cells. This strategy may be invaded by other organs, such as the liver or kidneys, if they are not functioning properly.

To understand how this might work, consider a simple game in which the heart and lungs are competing with the liver and kidneys for a limited supply of resources. The heart and lungs use a strategy of pumping oxygen-rich blood throughout the body, while the liver and kidneys use a strategy of filtering impurities from the blood. In this game, the heart and lungs are likely to have a higher fitness because their strategy is necessary for the survival of the body's cells.

Here is a simple example of a game.

| | Heart and Lungs | Liver and Kindey |
| --- | --- | ---|
| Heart and Lungs | -1, -1 | -10, 10 |
| Livery and Kidney | 10, -10 | -5, 5 |

In evolutionary game theory, the fitness of a strategy is typically quantified using the replicator equation, which is given by:

$$\dot{x_i} = x_i(\pi_i - \bar{\pi})$$

In this equation, $x_i$ represents the relative frequency of strategy $i$ in the population, $\pi_i$ is the average payoff for strategy $i$, and $\bar{\pi}$ is the average payoff for the population as a whole.

Another key tool used in evolutionary game theory is replicator dynamics, which is a set of equations that describe how the frequencies of different strategies in a population will change over time. Here is an example of the replicator dynamics equations:

$$ \frac{d\mathbf{x}}{dt} = \mathbf{x} \odot (\mathbf{A}\mathbf{x} - \bar{\mathbf{A}}\mathbf{x}) $$

This can be extended by techniques like the Nash equilibrium, which can be defined mathematically using the following equation:

$$ \text{Nash Equilibrium: } \mathbf{x}^* \text{ such that } \forall i, \mathbf{x_i}^* \in \arg\max_{\mathbf{x_i}} (\mathbf{A}_{i,\bullet}\mathbf{x}^*) $$

In this game, the numbers in each cell represent the payoffs for each pair of strategies. For example, in the top left cell, the numbers -1 and -1 represent the payoffs for the heart and lungs when both players use the same strategy.

In this particular game, the heart and lungs have a higher fitness because their strategy is necessary for the survival of the body's cells. However, if the liver and kidneys are not functioning properly, then their strategy may become more successful. This could lead to a shift in the population of organs, with more individuals adopting the strategy of the liver and kidneys. Over time, this could lead to a change in the overall strategy of the body, with a greater emphasis on filtering impurities from the blood.

# Depth

Exploring Evolutionary Game Theory in depth uses two core methods.

### Price Method

The Price equation, which describes how the genetic variation within a population will change over time. Here is an example of the Price equation:

$$ \frac{dV}{dt} = \mathbf{Cov}(\mathbf{f}, \mathbf{w}) $$

In these equations, $V$ represents the total genetic variation in the population, and $\mathbf{f}$ and $\mathbf{w}$ are vectors representing the fitnesses and frequencies of different genetic variants. The operator $\mathbf{Cov}$ represents the covariance between the two vectors.

The Price equation can be used to understand how the genetic variation within a population of organs will change over time in response to natural selection. It is an important tool for studying the evolution of organ systems and their interconnectedness.

### Monte Carlo Method

In these equations, $\mathbf{x}_n$ represents the current state of the system, and $\mathbf{r}_n$ is a random vector that is used to update the state of the system. The Monte Carlo method works by repeatedly updating the state of the system using random vectors and averaging the results to approximate the solution to the problem.

$$ \mathbf{x}_{n+1} = \mathbf{x}_n + \mathbf{r}_n $$

The Monte Carlo method can be used to study the evolution of organ systems in evolutionary game theory. For example, it can be used to simulate the interactions between different organs and their strategies over time, and to approximate the resulting evolution of the organ system. This can provide insight into the complex dynamics of organ evolution and their interconnectedness.

# Building Fleet

Fleet is an evolutionary game theory model that examines the interconnectedness of organ systems. 

### Individual Games

Games are played for a fixed number of rounds, and each organ has a strategy of either cooperating or defecting.

At each round of the game, the payoffs for each organ are computed based on their strategies. These payoffs are determined by a pre-defined payoff matrix that assigns a payoff to each combination of strategies. For example, if the brain cooperates and the heart defects, the payoff for the brain is 0 and the payoff for the heart is 5.

The code also includes a mutation mechanism, which randomly changes the strategies of the organs with a certain probability (the mutation rate). This simulates the process of evolution, where random mutations can lead to changes in the strategies of the organs over time.

At the end of each round, the payoffs for each organ are printed to the console. This allows the user to see how the payoffs change over time as the strategies of the organs evolve.

Games that evalute interactions between the Heart, Lungs and Kidney can be determined with this:

```cpp
...
void playRound(unordered_map<string, char>& strategies) {
  double random = (double)rand() / RAND_MAX;
  if (random < MUTATION_RATE) {
    strategies["heart"] = (strategies["heart"] == STRATEGY_COOPERATE) ? STRATEGY_DEFECT : STRATEGY_COOPERATE;
  }
  // continue this for all strategies
	...
  int payoff_heart, payoff_lungs, payoff_kidney;
  if (strategies["heart"] == STRATEGY_COOPERATE && strategies["lungs"] == STRATEGY_COOPERATE && strategies["kidney"] == STRATEGY_COOPERATE) {
  ...
  } else if (strategies["heart"] == STRATEGY_COOPERATE && strategies["lungs"] == STRATEGY_COOPERATE && strategies["kidney"] == STRATEGY_DEFECT) {
    // Heart and lungs cooperate, kidney defects
    ...
  } 
}
```

Similarly, games with the Brain and Heart may be determined with this:

```cpp
...
void playRound(unordered_map<string, char>& strategies) {
  double random = (double)rand() / RAND_MAX;
  if (random < MUTATION_RATE) {
    strategies["brain"] = (strategies["brain"] == STRATEGY_COOPERATE) ? STRATEGY_DEFECT : STRATEGY_COOPERATE;
  }
  ...

  random = (double)rand() / RAND_MAX;
...
  if (random < MUTATION_RATE) {
    strategies["heart"] = (strategies["heart"] == STRATEGY_COOPERATE) ? STRATEGY_DEFECT : STRATEGY_COOPERATE;
  }
  
  int payoff_brain, payoff_heart;
  if (strategies["brain"] == STRATEGY_COOPERATE && strategies["heart"] == STRATEGY_COOPERATE) {
    payoff_brain = 3;
    payoff_heart = 3;
  } else if (strategies["brain"] == STRATEGY_COOPERATE && strategies["heart"] == STRATEGY_DEFECT) {
    payoff_brain = 0;
    payoff_heart = 5;
  } else if (strategies["brain"] == STRATEGY_DEFECT && strategies["heart"] == STRATEGY_COOPERATE) {
  ...
}
```

At each round of the game, the payoffs for each organ are computed based on their strategies. These payoffs are determined by a pre-defined payoff matrix that assigns a payoff to each combination of strategies. For example, if the brain cooperates and the heart defects, the payoff for the brain is 0 and the payoff for the heart is 5.

The code also includes a mutation mechanism, which randomly changes the strategies of the organs with a certain probability (the mutation rate). This simulates the process of evolution, where random mutations can lead to changes in the strategies of the organs over time.

### Evaluating Effectiveness

The effectiveness directly analyzes the theorietically determined data.

```cpp
void compareResults(String strategies, double actual_heart, double actual_lungs, double actual_kidney) {
  double simulated_heart = 0;
  for (int i = 0; i < strategies.length(); i++) {
    if (strategies[i] == STRATEGY_COOPERATE) {
    ...
    } else if (strategies[i] == STRATEGY_DEFECT) {
    ...
    }
  }
  simulated_heart /= strategies.length();
  double mse_heart = pow(simulated_heart - actual_heart, 2);
  Serial.print(mse_heart);
  // continue for lung, brain or other organs
}
```

The code defines several assumptions and parameters for the simulation, such as the population size, the number of generations, and the mutation rate.

The code then generates theoretical data based on these assumptions and parameters, using a function called `generateTheoreticalFitness()`. This function produces a vector of theoretical fitness values for each generation of the simulation.

Next, the code runs the actual simulation by initializing a population of organisms and calling the `runSimulation()` function. This function simulates the evolution of the population over multiple generations, and returns a vector of actual fitness values for each generation.

After the simulation is complete, the code compares the theoretical and actual data by calculating the difference between the fitness values in each generation. This allows the user to see how closely the simulated data matches the theoretical predictions. `compareResults()` compares the simulated payoffs for each organ with the actual payoffs. This is done by computing the mean squared error for each organ, which is a measure of the difference between the simulated and actual payoffs. The function then displays the mean squared error.

# Resolution

The connection between organs is an important topic in evolutionary game theory. This is because organs are interdependent on each other, and the strategies they use can have a profound impact on their fitness and the overall functioning of the body.

One of the key ideas in evolutionary game theory is the concept of an evolutionarily stable strategy (ESS), which is a strategy that cannot be invaded by any other strategy. This means that if a population of players is using an ESS, then any individual who tries to use a different strategy will be at a disadvantage and will eventually be forced to switch back to the ESS. This can lead to the emergence of stable social structures and behaviors within a population.

This can provide insight into the complex relationships between different organs within the body, and may help to identify potential problems or areas for improvement. Existing research has explored intercellular interactions.

![[images/Pasted image 20221203215442.png]]

In order to study the evolution of strategies, evolutionary game theory makes use of tools from population dynamics and evolutionary biology, such as replicator dynamics and fitness landscapes. These tools allow us to track the evolution of strategies over time and understand how they interact with each other.

For example, in the simulation discussed earlier, the heart and the lungs had to make a decision about whether to cooperate or defect. If both organs chose to cooperate, they both received a payoff of 3. However, if one organ chose to cooperate and the other chose to defect, the organ that cooperated received a payoff of 0, while the organ that defected received a payoff of 5. This example shows how the strategies of organs can affect their payoffs and fitness. It also demonstrates the complex interconnectedness of organs, where the actions of one organ can have a significant impact on the payoffs of other organs.

The connection between organs is an important topic in evolutionary game theory, and has many implications for the study of organ evolution and the functioning of the body as a whole. By understanding the dynamics of organ evolution and their interconnectedness, we can gain valuable insights into how the body works and how it may evolve over time.

---