---
date: 2020-08-11
title: Neural Networks approximate any function
descript: '"Probably the main underlying reason behind the success of neural networks is the fact that they can represent any functional combination of input and output vectors. That is to say, the will approximate any function in the universe."'
---

The Universal Function Approximation theorem states that Neural Networks of increasing size and depth can approximate any function in the world. This is amazing.

[Multilayer perceptrons](/notes/multilayer-perceptron) (MLP) are the fundamental buildings blocks of a NN. NNs add MLPs side-by-side to create layers, and add more layers to create depth.

## Activation Functions
- ReLU
- TanH
- Sigmoid

## Loss Functions
- $\frac{1}{2}e^2$
- Softmax
	- $\sigma(z) = e^{z_i} (\Sigma^K_{j=1}e^{z_j})^{-1}$

	- $z$ is the input vector, $\in \{-\infty,\infty\}$, can be pos, neg, zero.
	- $\exp{z}$ is applied to each element of the input vector, gives a pos. value above 0, which will be small if the input was neg., large if the input was large. Still not in (0,1)
	- $\Sigma$ on bottom is the normalization term, ensures the output will sum to 1 in the range (0,1), making this a valid probability distribution.
- Cross-entropy
	- The cross-entropy between two probability distributions $p$ and $q$ over the same underlying set of events measures the average number of [bits](https://en.wikipedia.org/wiki/Bit "Bit") needed to identify an event drawn from the set if a coding scheme used for the set is optimized for an estimated probability distribution $q$, rather than the true distribution, $p$.
	- Basically, we want to figure out the true value, or label, $P$, and the predicted value, $Q$, multiply them together. (P,Q) = (1,1) -> loss is 0, it really penalizes the values when P gets low based on (-log(x)).
	- Has a linear gradient
	- $H(p,q) = - \sum_{X} P(x) log(Q(x))$
	- $H(p,q) = - \int_{X} P(x) log(Q(x)) dr(x)$
- Regularization
	- A technique that adds terms on to the end of a Neural networks Loss function to include more emphasis on the weight terms.
	- Similar to Lagrangian optimization in Microeconomics, where you maximize a *utility function* according to a *constraint*
	- max(*utility function*) + $\lambda$(constraint)
	- Typically, add a LP-Norm to the loss function


## Variations
Autoencoder
- A type of NN that attempts to learn a sparse representation of the data. This accomplishes dimensionality reduction.
- Takes in input vector x, turns it into reduced output y, and encodes y to return x as output.
- Useful for VAEs and GANs

Generative Adversarial Network
- A type of NN that trains two networks in tandem: a generator and a discriminator. Random inputs are passed to the generator, which creates new samples. The discriminator has to determine if input images are real data or fake (from the generator).
- CycleGANs add in a full cycle from input $x$ to output $y$ back to recovered input $\hat{x}$ with a loss term hoping that $y$ and $x$ can be recovered by passing backwards thru the net.

Extreme Learning
- A type of NN. In high-enough dimension space, any given vector can be mapped down to low-dimension (but still high) space, and generally the distances between points is preserved. This is because in large dimensions, most vectors are quasi-orthogonal with small inner products. Any two random vectors will be approximately orthogonal with probability $\approxeq$ 1
- Simply put:
	- Input Layer: $X$, dimension 1xN
	- Hidden Layer: random weight matrix $W$, dimension NxL
	- Output Layer: MLP learning linear decisions on dimension L
- This shows that just using random projects of $X$ from N onto L leads to great learning performance. Really interesting.

Convolution Neural Network
- A type of NN that uses convolution

U-Net
- A type of CNN with skip connections

Residual Net
- A type of NN that uses skip connections to deal with vanishing gradient problems. Made popular by the U-Net.
- How?
	- $x$ = input vector
	- $W$ = input scalar to match $R(x)$
	- $R(x)$ = residual component (activation before input is added)
	- $y$ = $H(x)$ = output
	- $ y = H(x) = R(x) + Wx $
	- newState = fx(oldState, input)

Fractionally Strided Convolution
	
- A type of NN similar to CNNs. Convolution typically uses a filter to go from larger image (e.g. 4x4) to a smaller image (e.g. 2x2). Convolution acts as a good filter across the image. This technique tries to go UP rather than down. The problem is we're trying to GAIN information (normally, more pixels). Basically, for any region of the initial image, we need to find the resulting image that would "convolve" to the initial image. You can set up the series of equations to basically make this all make sense. Aka run convolution in reverse.
- $ Y' = W X' $
- $ Z = W^T Y'$

Recurrent Network
- A type of NN that is temporal rather than feed-forward like an [multilayer perceptron](/blog/multilayer-perceptron).
- The output from one moment of time becomes the input to the next state. 
- This is called "feedback". The feedback can be weighted. Unity weights mean the output is directly passed to the inputs.
