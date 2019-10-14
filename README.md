# TextAttack

## Installation

You must be running Python 3.6+ to use this package. A CUDA-compatible GPU is 
optional but will greatly improve code speed.

```
conda create -n text-attack python=3.7
conda activate text-attack
pip install -r requirements.txt
mkdir outputs
```


## Features

### Models

We've also included a few pre-trained models for common
tasks that you can download and run out-of-the-box. However,
anything that overrides __call__, takes in tokenized text, and 
outputs probabilities works for us. This includes your favorite
models in both Pytorch and Tensorflow.

@TODO show examples of each in `examples/`.

### Attack Methods

We support the following attack methods:

- Greedy selection over all input words
- Greedy selection with Word Importance Ranking (["Is Bert Really Robust?" (Jin et al., 2019)](https://arxiv.org/abs/1907.11932))
- Genetic algorithm (["Generating Natural Language Adversarial Examples" (Alzantot et al., 2018)](https://arxiv.org/abs/1804.07998))

### Perturbations

An attack method selects the best possible perturbation from a set of potential perturbations. We support perturbations on the sentence, word, and character level.


#### Word Perturbations

- Counterfit synonym swap

### Constraints

Text input perturbations are only valid if they meet the constraints of the attack. This library supports constraints on the semantic, syntactic, and morphological level. Some constraints measure changes in the entire input, while others only take into account substitutions of a single word.

#### Semantics

##### Input-level Constraints
- Universal Sentence Encoding cosine distance

##### Word-level Constraints
- Word embedding nearest-neighbor distance

#### Syntax
- Grammatical errors induced, measured with [LanguageTool](https://languagetool.org/)

#### Morphology

### Datasets

We include a few popular datasets to get you started.

#### Yelp Sentiment Analysis

The [Yelp Sentiment Analysis dataset](https://www.yelp.com/dataset/challenge) includes inputs from yelp reviews manually labeled as positive (1) or negative (0).