What is the value of the start state in the MazeGrid environment for the
random policy (default discount factor γ = 0.9). Try different number
of episodes (use -k xxxx -q) and provide mean value and the standard
deviation over the episodes. Try also k= 10000.

```python gridworld.py -g MazeGrid -a random -k 10000 -q```

RUNNING 10 EPISODES
the value estimation for the start state 1)mean: 0.0079 2)std: 0.0157

RUNNING 100 EPISODES
the value estimation for the start state 1)mean: 0.0030 2)std: 0.0101

RUNNING 1000 EPISODES
the value estimation for the start state 1)mean: 0.0012 2)std: 0.0067

RUNNING 10000 EPISODES
the value estimation for the start state 1)mean: 0.0021 2)std: 0.0127

How many episodes do you need to be sure (confidence 95%) that your
mean estimate is within ±0.0004 of the true mean?

95% z=1.96

z*std/sqrt(k) <= 0.0004
1.96 * 0.0127/sqrt(k) <= 0.0004
k>=(1.96 * 0.0127/0.0004)**2
k>=3873

Do the same with the DiscountGrid for a discount γ = 0.95. How many
episodes do you need to be sure (confidence 95%) that your mean estimate
is within ±0.1 of the true mean?

```python gridworld.py -g DiscountGrid -d 0.95 -k 10000 -q```

RUNNING 10 EPISODES
the value estimation for the start state 1)mean: -4.9312 2)std: 4.0435

RUNNING 100 EPISODES
the value estimation for the start state 1)mean: -6.2578 2)std: 3.8662

RUNNING 1000 EPISODES
the value estimation for the start state 1)mean: -6.4245 2)std: 3.7675

RUNNING 10000 EPISODES
the value estimation for the start state 1)mean: -6.4090 2)std: 3.8160

95% z=1.96

z*std/sqrt(k) <= 0.1
1.96 * 3.8160/sqrt(k) <= 0.1
k>=(1.96 * 3.8160/0.1)**2
k>=5595