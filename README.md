
# FlexER: Flexible Entity Resolution

FlexER is a mehthod for solving multiple intents entity resolution (MIER) problem.
FlexER combines independent intent solutions to improve outcome to multiple resolution problems, by using graph convolutional network (GCN).
The independent intent solutions are based on solutions to universal ER tasks, such that every matcher which can provide a latent representation of record pairs can be adjusted to our framework.
In this work, we use [DITTO](https://github.com/megagonlabs/ditto), the state-of-the-art in universal ER. Specifically, we use the final embedding of the special token [cls](used for classification) as a record pair representation, and inject it into the FlexER system.

Our paper is currently under review for [KDD 2021](https://www.kdd.org/kdd2021/).


![mier_system](mier_system.JPG)

## MIER: Multiple Intents Entity Resolution
We offer to extend the universal view of ER, pointedly reflected in the use of a single mapping from records to real-world entities, to include multiple intents.
To better understand the meaning of multiple intents, note that the universal view of ER implicitly assumes a single entity set by which the ER solution must abide.
Such an entity set is not explicitly known, yet typically referred to abstractly as a “real-world entity." We argue that an entity set of choice may vary according to user needs and different users may seek different solutions from the same dataset.

A one-size-fits-all resolution provides an adequate solution for universal ER, a standalone task with a single equivalence intent.
Yet, some data cleaning/integration challenges (recall Section 1.1) may involve multiple intents. Therefore, instead of performing a universal ER, we argue for enhancing ER to support multiple outcomes for multiple intents. 
A MIER involves a set of (possibly related) entity mappings for a set of intents E = {𝐸1, 𝐸2, · · · , 𝐸𝑃 }, offering multiple ways to divide 𝐷, each serving as a solution for a
respective intent.

For further details and official definitions, please refer to our paper (currently under review).

## Methodology
Our proposed solution to the problem of MIER casts the problem as a multi-class multi-label task. As a baseline solution, we first propose to treat multiple intents as a set of independent single intent problems, where each intent is considered individually and provides an independent solution for single intent ER (using [DITTO](https://github.com/megagonlabs/ditto)).

We then describe Flexible Entity Resolution (FlexER), a flexible algorithm to the MIER problem, which constructs an intents graph using record pairs representations and applies a graph convolutional network (GCN) to provide improved resolutions.

FlexER utilizes the interrelations between intents using the matchers to enrich the ability of the MIER solution as well as the resolution of the individual intents. FlexER
builds upon the solutions of [DITTO](https://github.com/megagonlabs/ditto), training 𝑃 independent matchers, one for each intent. 
Rather than solely depend on the final predictions of the independent matchers, FlexER employs the record pairs representations to construct an intent graph that
is fed into a graph convolutional network (GCN) structure. 
Given an input record pair, an undirected graph is created. The nodes of the graph correspond to the record pair representations for each intent, and the edges to the interrelations among the intents (calculated as the Pearson correlation between the intents' labels over the training set).

The GCN inference is performed using a message passing algorithm following [Kipf & Welling](https://arxiv.org/abs/1609.02907).

For further details and official definitions, please refer to our paper (currently under review).
 
  
![FlexER_small](FlexER_small.JPG)

## Requirements
1. The same as mentioned in [DITTO](https://github.com/megagonlabs/ditto)
2. [PyTorch Geometric (Version 1.6.3)](https://pytorch-geometric.readthedocs.io/en/latest/#)

## Getting Started

### Datasets

### training with Ditto

### Yielding prediction vectors

### Running FlexER


