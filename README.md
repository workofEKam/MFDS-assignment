# probability-simulator
simulates binomial and geometric probability with animation

# Get started
- clone this repository and install the necessary dependecies

```bash
pip install -r requirements.txt
```

# Distributions
## Geometric distribution
This will run the probability until you get n amount of successes and will record the amount of times you have to run the probability until you get a success.
For example if you flip a coin over and over again until you get a heads and got a heads on the **3rd** try. The bar at **3** will increase by one.
Find more about Geometric distribution here: https://en.wikipedia.org/wiki/Geometric_distribution 

## Binomial distribution
Thiswill run the probability n amount of times and record the number of successes into the bar.
For example if you flip a coin **10** times and got **6** heads, the bar at **6** will increase by 1.

Find more about Binomial distribution here: https://en.wikipedia.org/wiki/Binomial_distribution

## Initializing Geometric distribution
## Geometric
```python
import probsim
X = probsim.GeometricDistribution(0.3, 10_000)
# 0.3 is the probability, 10_000 is the max frame and is also the amount of successes for this simulation
```
## Binomial
```python
Y = probsim.BinomialDistribution(30, 0.3, 1000)
# 30 is n, 0.3 is p, 1000 is the max frames or the number of sessions.
```


## Simulating 
This will run the probability and graph it out.
### Geometry
```
X.simulate()
```
Output:

![image](https://github.com/k1m-ch1/probability-simulator/assets/116435978/93af9940-c8db-486d-9e5d-75ee75094b16)

### Binomial
```python
Y.simulate()
```
Output:

![image](https://github.com/k1m-ch1/probability-simulator/assets/116435978/428cded9-df5c-44f9-bd33-9300cd50fef5)


## Theoretical Binomial Distribution
This won't run the probability but will give the theoretical probability that you will get. According to this formula
### Geometric
$$
P(X = k) = (1-p)^{k-1} \times p
$$
```python
X.get_theoretical_probability()
```
Output:

![image](https://github.com/k1m-ch1/probability-simulator/assets/116435978/b8843239-d249-4b56-80a5-dadc528c1706)
### Binomial
$$
P(Y = k) =\frac{n!}{(n-k)!k!}\times p^k (1-p)^{n-k}
$$
```python
Y.get_theoretical_probability()
```

![image](https://github.com/k1m-ch1/probability-simulator/assets/116435978/ee55555c-3c73-4837-a17c-76bcdd5441ee)


## Playing adding value animation
This will add the value one by one until the maximum number of successes is reached (aka the max frame).
### Geometric
```python
# If return_anim is true, then it won't play the animation and will return the animation object, otherwise it will play the animation. Default is False
X.play_adding_value_animation(return_anim=True)
```
Output:

![geometric_distribution_adding](https://github.com/k1m-ch1/probability-simulator/assets/116435978/d0c26b58-8bb7-4879-8f44-7021ec1a1e32)

### Binomial
```python
Y.play_adding_value_animation(return_anim=True)
```

Output:

![demo_binomial_distribution](https://github.com/k1m-ch1/probability-simulator/assets/116435978/62803ba1-86bd-427b-8e7b-acb0d6b8f2b4)


## Play changing probability animation
This will change the probability by 0.01 every frame.
### Geometric
```python
X.play_changing_probability_animation(return_anim=True)
```
Output:

![demo_geometric_distribution_15_fps](https://github.com/k1m-ch1/probability-simulator/assets/116435978/5d67caec-7f0d-4f85-80a9-69a1536f9fa2)

### Binomial
```python
Y.play_changing_probability_animation(return_anim=True)
```
Output:

![Binomial_distribution_changing_p](https://github.com/k1m-ch1/probability-simulator/assets/116435978/1bf157f7-aec1-4ae0-916c-fd7bb920d967)

## Saving animation
This animation is of the parent class so it applies to every child class
**Note:** there must be a directory called 'saved_animation'
```python
X.save_animation(X.play_adding_value_animation(return_anim=True), 'geometric_distribution_adding', fps=15)
```
