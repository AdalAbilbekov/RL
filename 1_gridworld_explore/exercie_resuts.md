### Ex-1

$$
G = a_1 + \gamma a_2 + \gamma^2 a_1 + \gamma^3 a_2 + \dots
  = \sum_{k=0}^{\infty} \gamma^{2k}\,(a_1 + \gamma a_2)
  = \frac{a_1 + \gamma a_2}{1 - \gamma^2}, \gamma < 1
$$

$\pi_{\text{left}}$: $a_1 = 1,\ a_2 = 0$

$\pi_{\text{right}}$: $a_1 = 0,\ a_2 = 2$

$\gamma \in \{0,\ 0.9,\ 0.5\}$

**$\gamma = 0$**

$$
G_{\text{left}} = \frac{1 + 0}{1 - 0} = 1 \qquad
G_{\text{right}} = \frac{0 + 0}{1 - 0} = 0
$$

Optimal policy: $\pi_{\text{left}}$.

**$\gamma = 0.9$**

$$
G_{\text{left}} = \frac{1 + 0}{1 - 0.81} = \frac{1}{0.19} \approx 5.26 \qquad
G_{\text{right}} = \frac{0 + 2 \cdot 0.9}{1 - 0.81} = \frac{1.8}{0.19} \approx 9.47
$$

Optimal policy: $\pi_{\text{right}}$.

**$\gamma = 0.5$**

$$
G_{\text{left}} = \frac{1 + 0}{1 - 0.25} = \frac{1}{0.75} = \frac{4}{3} \approx 1.33 \qquad
G_{\text{right}} = \frac{0 + 2 \cdot 0.5}{1 - 0.25} = \frac{1}{0.75} = \frac{4}{3} \approx 1.33
$$

Both policies are optimal

### Ex-2.2

What is the value of the start state in the MazeGrid environment for the
random policy (default discount factor γ = 0.9). Try different number
of episodes (use -k xxxx -q) and provide mean value and the standard
deviation over the episodes. Try also k= 10000.

```python gridworld.py -g MazeGrid -a random -k 10000 -q```

10 EPISODES: 1)mean = 0.0079 2)std = 0.0157

100 EPISODES: 1)mean = 0.0030 2)std = 0.0101

1000 EPISODES: 1)mean = 0.0012 2)std = 0.0067

10000 EPISODES 1)mean = 0.0021 2)std = 0.0127

How many episodes do you need to be sure (confidence 95%) that your
mean estimate is within ±0.0004 of the true mean?

For a 95% confidence level, $z = 1.96$.

$z \cdot \frac{\sigma}{\sqrt{k}} \le 0.0004$

$1.96 \cdot \frac{0.0127}{\sqrt{k}} \le 0.0004$

$k \ge \left( \frac{1.96 \cdot 0.0127}{0.0004} \right)^2$

$k \ge 3873$

Do the same with the DiscountGrid for a discount γ = 0.95. How many
episodes do you need to be sure (confidence 95%) that your mean estimate
is within ±0.1 of the true mean?

```python gridworld.py -g DiscountGrid -d 0.95 -k 10000 -q```

10 EPISODES 1)mean = -4.9312 2)std = 4.0435

100 EPISODES 1)mean = -6.2578 2)std = 3.8662

1000 EPISODES1)mean = -6.4245 2)std = 3.7675

10000 EPISODES 1)mean = -6.4090 2)std = 3.8160

For a 95% confidence level, $z = 1.96$.

$z \cdot \frac{\sigma}{\sqrt{k}} \le 0.1$

$1.96 \cdot \frac{3.8160}{\sqrt{k}} \le 0.1$

$k \ge \left( \frac{1.96 \cdot 3.8160}{0.1} \right)^2$

$k \ge 5595$