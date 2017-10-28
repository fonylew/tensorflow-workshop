# Generative Model
## (Unsupervised learning)



Ian Goodfelllow,  Google Brain

If AI can understand it, AI can gernerate it.

Semi-supervised learning
- reinforcement learning

==> artwork, super-resolution, colorization
Explicit
|- Tractable density (calculatable likelihood) --> PixelRNN
|- 
 - Variational autoencoder
 - Markov Chain

# Pixel RNN
Fully Visible Belief Networks (FVBN)
Chain rules --> decompose likelihood function
** maximize likelihoodd function **

define previous pixels
RNN (LSTM) --> dependency on previous pixel
order pixel from top left [Sequential]

Pixel CNN
softmax losss at each pixel 
==> generate pixel from previous pixel

pro
- explicitly compute likelihood
- good evaluation metric
- good samples

Cons
- slow due to  sequential generation O(n)
- generation  is not controlled by a * laten code *

## WaveNet
(Google DeepMind)
use for sound generating

# VAE : Variational Autoencoder
** Autoencoder ** capture variation in data (unsupervised learning)
Input(x) -- Encoder --> z -- Decoder --> Output(y)
			^ Latent Variable/ Embededing /Feature
maximized auto encoder
initialize a supervised model:
	from embeding and classify
## VAEs
Probabilistic spin on autoencoders
unobserved (latent)
z    -- Decoder Network-->  x
true prior		    true conditional P(x|z)	

Intactable --> Posterior Density
P(z|x) = P(x|z)P(z) / P(x)

Log Likelihood
Dkl -> KL divergence : nonnegative

tractable lowerbound : E[logp(x(i)|z)- Dkl(q(z|x(i)||p(z))

# Data  Generation
- use the generated  network
ex - MNIST (number)
   - generate degree of smile based on 

Pros
- allows ...

Cons
- blurrier and lower quality	


Sketch-RNN (Google Magenta - AI in art and musics)
Quick Draw(quickdraw.withgoogle.com/data)
Bidirectional RNN
- Seq-to-Sql VAE
https://github.com/tensorflow/magenta-demos/
github.com/tensorflow/magenta-demos/blob/master/jupyter-notebook

Conditional Reconstruction --> ได้งาน art ที่ unique

# Word2Vec
Latent Variable is represented in Vector

Interpolate

# GenerativeAdversarialNetwork(GAN)
Yann LeCun
Give up on explicitly modeling density
Game Theory (2-player game)

# The Two-Player Game
- Generaor Network

- Discriminator Network
	Fake or Real?
Transform Random noise into sample
## Minimax
Objective function
Training GAN

# GAN
high-res image generating

DCGAN: Deep Convolutional Generative Adversarial Networks
Vectorspace Arithmic

Pros
- Beautiful, state-of-the-art samples

Cons
- Trickier / more unstable to train

the-gan-zoo
Neural Face


