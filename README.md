
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

For further details and official definitions, please reffer to our paper (currently under review).

## Methodology


## Requirements

## Getting Started

## Datasets

## training with Ditto

## Yielding prediction vectors

## Running FlexER


