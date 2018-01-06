# PAPER SUMMARIES

A list of some notable (*) or interesting papers in DL, with a short description loosely following this MD format
```
'***title, first author et al, year**

- link: <>
- code: <>
- summary: 
- approach:  
- other:
```
(note: sometimes et al. ommitted for brevity)

## GANS

***Generative adversarial nets, Goodfellow et al, 2014**

- link: <http://papers.nips.cc/paper/5423-generative-adversarial-nets.pdf>
- code: several flavors using various frameworks available on github ...
- summary:  original paper on GANs, learns 2 networks (a generator and a discriminator) with competing losses. The aim of the generator network is to map a random vector to a realistic image, the aim of the discriminator is to distinguish the generated from the real images.
- approach:  
-  idea is to compete a generative model/network that does image synthesis and a discriminative model (which detects what is "fake/synthetic") both networks are "joined at the hip" via competing loss functions and a training procedure that is using minimax two player game: this trains / updates in alternance the weights of the image synthesis network, and the discriminator network. The end product of the procedure is both a discriminative and a generative model that become ever more competent. This two players minimax learning procedure is a foundation for the idea of many other subsequent papers using this "adversarial training" technique for improving the performance of a discriminative model.

***Learning from Simulated and Unsupervised Images through Adversarial Training, Shrivastava et al, Apple, 2017**

- link: <https://arxiv.org/abs/1612.07828>
- summary: a hybrid physics simulation and GAN-like approach to novel image generation
- approach:  modification to GAN loss function including: (i) a 'self-regularization' term, (ii) a local adversarial loss, (iii) updating the discriminator using a history of refined images. 
- other: 
- learns a model that improves the realism of synthetic images from a simulator using unlabeled real data
by using the annotation information from the simulated data
- takes simulated + label data through a net that improves 'realism' (called refiner net), then use adversarial training on it (via a real vs simulated discriminative net).

***Improved techniques for training GANs, Salimans et al, 2016**

- link: <http://papers.nips.cc/paper/6125-improved-techniques-for-training-gans.pdf>
- summary: 
- approach:  
- other

**Unsupervised representation learning with deep convolutional generative adversarial networks, A. Radford et al, 2015**

- link <https://arxiv.org/pdf/1511.06434v2>
- summary: details some improvement strategies on GANs net architecture
- approach:  
- uses all convolutional network
- uses batch normalization
- uses visualization. 
- other: 

## Unsupervised, semi-supervised, X-shot (zero, one, adaptive), generative

*** zero shot learning: the good, the bad and the ugly, 2017**

- link <>
- summary: evaluates performance of various ZS approaches. 
- approach: embedding in joint image-text space
- summary: 
- approach:  

**learning features by watching objects move, Girshick, dollar, darell, 2017**

- goal: unsupervised segmentation
- approach: low level motion feature based segmentation to train a CNN to do segmentation on static frames
- compares to recent work on unsupervised learning
- application: novel class detection

**Zero-Shot Learning Through Cross-Modal Transfer, 2013**

- link <https://arxiv.org/pdf/1301.3666.pdf>
- summary: using outlier detection in the semantic space to improve performance of seen+unseen class classifier
- approach: embedding in joint image-text space
- summary: 
- approach:  
- other: 

***Building high-level features using large scale unsupervised learning, Le et al, 2012**

- link: <http://arxiv.org/pdf/1112.6209>
- summary: builds feature detectors from unlabeled data. A face detector built without using any labeled faces
- approach:  
- other:

***pixel recurent neural networks, van der ord et al, google, 2016**

- link <http://arxiv.org/pdf/1601.06759v2.pdf>
- summary:  goal is to synthesize images, takes causal model of pixel generation.
- approach:  reminiscent of MRF uses recurrent nets (eg LSTMs) to predict each pixels in a causal fashion.
- other: 

***Deep Photo Style Transfer, Luan et al, 2017**

- link: <http://arxiv.org/pdf/1703.07511v1.pdf>
- summary: style transfer via CNN
- approach: constrains transformation from input to output to  locally affine in colorspace
- express that constraint as a custom CNN layer through which they can then backpropagate
- other:

**Auto-encoding variational Bayes, Kingma et al, 2013**

- link <http://arxiv.org/pdf/1312.6114>
- summary: 
- approach:  
- other: 


***DRAW: A recurrent neural network for image generation, Gregor et al, 2015**

- link <http://arxiv.org/pdf/1502.04623>
- code <https://github.com/ericjang/draw>
- summary: a image synthesis approach based on autoencoder framework using attention mechanism
- approach:  
- other: 

**isolation forest, liu, 2008**

- link <https://cs.nju.edu.cn/zhouzh/zhouzh.files/publication/icdm08b.pdf>
- summary: an original idea for anomaly detection based on building trees and hypothesizing the anomalies must stand isolated branches close to the root
- build a tree, e.g. a CART based on some features, it should be the case the anomaly stand on their own at the top (because there are few of them and they are distinct)
- use of forest of these

## DRL

**Leveraging deep reinforcement learning for reaching robotic tasks, Katyal et al., 2017**

- link: <>
- citation [@katyal2017leveraging]
- summary: control policy that is robust to changes and does not need calibration. Applied to reaching robotic tasks.
- approach: uses DRL and DQL 

**Collaborative Deep Reinforcement Learning for Joint Object Search, Kong et al, 2017**

- citation: [@kong2017collaborative]
- summary: active search of interactive object, eg. situations where different objects often appear with certain correlated patterns, e.g. person riding bicycle, cups on table
- approach: collaborative multi-agent DRL, multi-agent Q-learning, 

**Active object localization with deep reinforcement learning., Caicedo et al, 2015**

- cite: [@caicedo2015active]
- summary: DRL applied to active search of object
- approach: BB modified according to discrete action space, size 9, {move right, move left, move up, move down, scale bigger, scale smaller, aspect ratio change fatter, aspect ratio change taller, trigger}
- deep Q-learning
- reward is based IOU

**Mitigation of Effects of Occlusion on Object Recognition with Deep Neural Networks through Low-Level Image Completion, Chandler et al, 2016**

- cite: [@chandler2016mitigation]
- link <https://www.hindawi.com/journals/cin/2016/6425257/>
- summary:  object recognition via DCNN is affected by occlusion 
- approach: provides new dataset that emphasizes occlusion and methods to address this, including preprocessing by segmenting occlusion and inpainting.

## Adverserial

***Deep neural networks are easily fooled: High confidence predictions for unrecognizable images ,  Nguyen et al, 2015**

- link:
- summary:


## Face

**Neural Face Editing with Intrinsic Image Disentangling, samaras et al, 2017**

- link:
- summary: 
- uses GANs to des-entagle latent representation of face so that can keep surface normals fixed while changing some semantic properties like facial expression (smiling) or presence of glasses or age
- learns useful manifold of facial appearance
- approach:
- uses (approximate) models for face wrt to intrinsic face prop- erties including: geometry/surface normals, material properties/albedo, illumination
- network explicitly infers these properties 
-  net does forward rendering model that reconstructs image
- uses priors on these properties
- ensures fidelity by adversarial supervision
- uses mating to separate foreground vs background
- "We show that by constraining physical properties that do not affect the target edits, we can achieve significantly more realistic results compared to other learning-based face editing approaches."

**regularizing face verification networks for pain, Hager, 2017**

- link: https://arxiv.org/pdf/1702.06925.pdf
- summary:
- method:

## Classification

***Revisiting Unreasonable Effectiveness of Data in Deep Learning Era, Sun et al., 2017**

- link <https://arxiv.org/pdf/1707.02968.pdf>
- summary: considers needs for large datasets
- approach:
- other:
	- found that performance increases somewhat logarithmically based on volume of training data. 
	- pre-training helps
	- uses JFT-300M Dataset

**Fast Video Classification via Adaptive Cascading of Deep Models, cvpr 2017, krishamurphy **

- summary: 
- approach:
- online bandit setup
- structure the classifier as a cascade (or tree [30]) of simple classifiers such that “easy” examples lead to early exits and are therefore classified faster

**Counting Everyday Objects in Everyday Scene, Chattopadhyay, cvpr 2017**

- summary: goal is to count objects
- approach:
- naive would be to use detection
	- instead replicates subitizing – "the ability of humans to make quick assessments of counts given a perceptual signal, for small count values"
	- problem is solved via subdividing image into grid cells and regressing inside each cell count of objects
	- uses LSTM
- possible applications: object detection

**Integration of Dynamic Vision Sensor with Inertial Measurement for Electronically Stabilized Event-Based Vision, Delbruck**

- http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=6865714
- goal: de-smearing/stabilization of DVS input to do parallalx/stereo
- approach: uses inertial sensor to estimate rotation, derotate

**Cognitive Mapping and Planning for Visual Navigation**

-summary:
- an architecture that learns to map first-person views and plans a sequence of actions towards goals in the environment
- approach:
-  uses unified architecture for mapping and planning, such that the mapping is driven by the needs of the planner, and a spatial memory with the ability to plan given an incomplete set of observations about the world. 
-  uses value iteration as planning algorithm but crucially use a trainable, differentiable and hierarchical version of value iteration.


## RNN, speech, NLP

***A Knowledge-Grounded Neural Conversation Model, Ghazvininejad et al, 2017**
- link <https://arxiv.org/pdf/1702.01932>
- summary:
- approach
- other:
 
## Segmentation, FCNs

## RCNNs, object detection, tracking

## Other

***MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications, Howard et al, 2017**

- link <https://arxiv.org/pdf/1704.04861.pdf>
- summary:  goal is embedded/mobile deployments of DNN
- approach: hyper-parameters that trade off latency and accuracy
- other:
	
**The efficient estimation of word representations in vector space, 2013, mikolov**

- summary: goal is learn high quality words vectors from very large datasets, 
-  aim to preserve vector operations (offsets) eg vector(”King”) - vector(”Man”) + vector(”Woman”) = vector that is closest to the vector(Queen) 
- techniques based on contious bag of word model (predicts current word based on context)
- continous skip-gram

# applications to medical, bio, chem

**Deep-Learning Based, Automated Segmentation of Macular Edema in Optical Coherence Tomography, lee, bioarxiv, 2017**
- link <https://www.biorxiv.org/content/biorxiv/early/2017/05/09/135640.full.pdf>
- summary: macular edema segmentation in OCT 
-  summary:
- 1289 OCT scans, DICE $DICE \lt [0.0703, 0.911]$, comparable to human performance, 3 annotators
- U-Net like convnet


### Other themes
Training practical, transfer learning, generalization
Constrained Nets (quantization, XNOR, ...)
Bio-inspired methods
Mathematical analysis in machine learning
Frameworks
