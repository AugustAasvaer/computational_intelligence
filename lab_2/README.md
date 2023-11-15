# LAB 2

## General Information
- The sole contributor to this work has been myself.
- All techniques have been implemented as explained in the lectures.
- The only external source used was [Wikipedia](https://en.wikipedia.org/wiki/Nim) to learn the rules of the game Nim, as well as the expert strategy.

## About the Implementation of the Rule-Based Expert Strategy
- The expert strategy utilizes the Nim sum strategy to choose the best move. As this implementation of Nim is a misère game (the one who takes the last set of sticks loses), there are some edge cases in which the strategy deviates from using the Nim sum to make a move. These cases occur when there is only one heap with a value higher than 1. In this scenario, the best move depends on whether the number of heaps with the value of 1 is odd or even. The strategy used to implement this was found at [Wikipedia](https://en.wikipedia.org/wiki/Nim).

## About the Implementation of GA
- The individuals have a genotype consisting of two lists: `heap_genome` and `amount_genome` with randomly initialized values between [0, 1]. These values represent the individual's propensity to choose a given heap and take a given amount from that heap.

- If `heap_genome[1] = 0.95`, given that the heap amount is not 0, the individual will choose this heap 95% of the time. If `amount_genome[1]` is 0.65, the individual will choose a number, x, from a truncated normal distribution with a mean of 0.65 and a variance of 0.15. Later, this number is multiplied by the highest possible number in the heap (`max(K, nim_row[1])`), with the lowest possible return value of 1 for the amount.

- Reproduction is done using the tournament method, where candidates for the tournament are chosen at random. It is important to note that both the evolution of the population and the evaluation are stochastic, as opposed to the regular implementation in which evolution is stochastic and evaluation is deterministic.

## Results
- The GA has a 100% win rate against the Gabriele strategy and approximately a 60% win rate against the random strategy.
- Several parameters could be tweaked to try to increase this win rate, for example, changing the parameters of the `choose_amount()` function, the population size, offspring size, and selective pressure, etc.
