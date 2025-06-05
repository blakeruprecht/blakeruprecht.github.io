---
title: Neural network
date: 2020-08-11
descript: '"The main underlying reason behind the success of neural networks is the fact that they can represent any functional combination of input and output vectors. That is to say, the will approximate any function in the universe."'
---


Neural networks are universal function approximators, according to the Universal function approximation theorem. Neural Networks eventually got deeper and more sophisticated, becoming the single most useful tool for artificial intelligence.

## The Perceptron (I'm just P), basically a straight line
Similar to a brain neuron. The perceptron is basically a function that fits a straight-line relationship between a range of input values and some corresponding output values. 

For example, to represent no relationship between input and output, you would have a neuron that outputs Y = 0 for every input value X. This means nothing you can input would ever light up that neuron.

OUTPUT = ACTIVATION_FUNCTION(INPUT x WEIGHTS + BIAS)
- X = INPUT = either a scalar (a single number, e.g. X=[37.42]), or a vector (a row of numbers, e.g. x=[37.42, -0.029, 0]). 
- W = WEIGHTS = a matching column of numbers, either scalar (e.g. W=[-0.55]) or vector (e.g. W = [-0.24, 0.97, 0.01]). 
- Phi = ACTIVATION_FUNCTION = a function that takes input XW and outputs Y
- 
- a function that transforms input values from [-Infinity, +Infinity] and maps them perfectly onto values from [-1, 1] so that no matter what the input/weight values end up being, the output value, Y, always stays in the range [-1, 1]. If you choose to use a different PHI, you can output values on the range [0, 1]. This way, you can determine the "activation intensity" of this perceptron
- Y = OUTPUT


## Multilayer-Perceptron (MLP), a long row of straight line warriors


## Neural Network (NN), multiple long rows, a whole damn army of straight lines


### Neural Network Variations
Autoencoder
- A type of NN that attempts to learn a sparse representation of the data. This accomplishes dimensionality reduction.
- Takes in input vector x, turns it into reduced output y, and encodes y to return x as output.
- Useful for VAEs and GANs

Generative Adversarial Network (GAN)
- A type of NN that trains two networks in tandem: a generator and a discriminator. Random inputs are passed to the generator, which creates new samples. The discriminator has to determine if input images are real data or fake (from the generator).
- CycleGANs add in a full cycle from input $x$ to output $y$ back to recovered input $\hat{x}$ with a loss term hoping that $y$ and $x$ can be recovered by passing backwards thru the net.

Extreme Learning
- A type of NN. In high-enough dimension space, any given vector can be mapped down to low-dimension (but still high) space, and generally the distances between points is preserved. This is because in large dimensions, most vectors are quasi-orthogonal with small inner products. Any two random vectors will be approximately orthogonal with probability $\approxeq$ 1
- Simply put:
	- Input Layer: $X$, dimension 1xN
	- Hidden Layer: random weight matrix $W$, dimension NxL
	- Output Layer: MLP learning linear decisions on dimension L
- This shows that just using random projects of $X$ from N onto L leads to great learning performance. Really interesting.

Convolution Neural Network (CNN)
- A type of NN that uses convolution, a 2D-representation of input vectors

U-Net
- A type of CNN with skip connections

Residual Net (ResNet)
- A type of NN that uses skip connections to deal with vanishing gradient problems. Made popular by the U-Net.
- How?
	- $x$ = input vector
	- $W$ = input scalar to match $R(x)$
	- $R(x)$ = residual component (activation before input is added)
	- $y$ = $H(x)$ = output
	- $$ y = H(x) = R(x) + Wx $$
	- newState = fx(oldState, input)

Fractionally Strided Convolution
	A type of NN similar to CNNs. Convolution typically uses a filter to go from larger image (e.g. 4x4) to a smaller image (e.g. 2x2). Convolution acts as a good filter across the image. This technique tries to go UP rather than down. The problem is we're trying to GAIN information (normally, more pixels). Basically, for any region of the initial image, we need to find the resulting image that would "convolve" to the initial image. You can set up the series of equations to basically make this all make sense. Aka run convolution in reverse.
- $$ Y' = W X' $$
- $$ Z = W^T Y'$$

Recurrent Network
- A type of NN that is temporal rather than feed-forward like an [[multilayer perceptrons]].
- The output from one moment of time becomes the input to the next state. 
- This is called "feedback". The feedback can be weighted. Unity weights mean the output is directly passed to the inputs.


## Appendix: the Math

### Perceptron

- $\mathbf{x}$ = input vector (e.g. $\mathbf{x}=[0.3, 5.4, 156.1]$) of length $N$ ($N=3$ in this e.g.), $\mathbf{x} \in [-\infty,\infty]$, can be normalized to [-1,1]$ or $[0,1]$

- $\mathbf{w}$ = weight vector of length $N$ in the range $[0,1]$

- $\sigma( )$ = activation function (typically ReLU, tanh, sigmoid, etc.)

- $y$ = output scalar in [-1,1]

- $\hat{y}$ = label scalar (the right answer)

- $e()$ = error or loss function (typically Mean Squared Error as shown here)

$$ y = \sigma(w^T \cdot x) $$
$$ e = \frac{1}{2}(\hat{y} - y)^2$$

#### Options for Activation Functions
So instead of letting y run hog-wild between `-INF` and `+INF`, we restrict y to values between -1 and 1. This is called normalizing the output. Why? I think because it's just easier to deal with than collecting a bunch of data and constantly scaling to the maximum and minimum data points. Instead, you can just tune the slope of these activation functions to adjust how sensitive the activation function should be -- it can accomadate input ranges from -INF to +INF, 0 to 40, -143 to -135, -2 to 59,001. You get the gist?

- ReLU
- TanH
- Sigmoid
#### Options for Loss Functions
- (1/2)e^2
- Softmax
	- $$
\sigma(z)_i = \frac{\exp{z_i}}{\Sigma_{j=1}^K \exp{z_j}}
$$
	- $z$ is the input vector, $\in \{-\infty,\infty\}$, can be pos, neg, zero.
	- $\exp{z}$ is applied to each element of the input vector, gives a pos. value above 0, which will be small if the input was neg., large if the input was large. Still not in (0,1)
	- $\Sigma$ on bottom is the normalization term, ensures the output will sum to 1 in the range (0,1), making this a valid [[Probability distribution]].
- Cross-entropy
	- The cross-entropy between two probability distributions $p$ and $q$ over the same underlying set of events measures the average number of [bits](https://en.wikipedia.org/wiki/Bit "Bit") needed to identify an event drawn from the set if a coding scheme used for the set is optimized for an estimated probability distribution $q$, rather than the true distribution, $p$.
	- Basically, we want to figure out the true value, or label, $P$, and the predicted value, $Q$, multiply them together. (P,Q) = (1,1) -> loss is 0, it really penalizes the values when P gets low based on (-log(x)).
	- Has a linear gradient
	- $$H(p,q) = - \sum_{X} P(x) log(Q(x))$$
	- $$H(p,q) = - \int_{X} P(x) log(Q(x)) dr(x)$$
- Regularization
	- A technique that adds terms on to the end of a Neural networks Loss function to include more emphasis on the weight terms.
	- Similar to Lagrangian optimization in Microeconomics, where you maximize a *utility function* according to a *constraint*
	- max(*utility function*) + $\lambda$(constraint)
	- Typically, add a LP-Norm to the loss function
	- $$||x||_p = \left( \sum_{i=1}^n |x_i|^p \right)^{\frac{1}{p}}$$

### Multilayer Perceptron (MLP)
A type of NN that implements multiple layers of the basic perceptron. 
