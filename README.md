# Efficient Similarity Measurement for High-Dimensional Embeddings using Geometrically-based 2-bit Quantisation

This repo contains the code that was used in the following paper:

    Efficient Similarity Measurement for High-Dimensional Embeddings using Geometrically-based 2-bit Quantisation

    Richard Connor (rchc@st-andrews.ac.uk)
    Alan Dearle (al@st-andrews.ac.uk)
    & Ben Claydon (bc89@st-andrews.ac.uk)

    School of Computer Science
    University of St Andrews
    St~Andrews
    KY16 9SS 
    Scotland,
    UK

Abstract
--------
Our context of interest is the measurement of similarity within high-dimensional spaces, in particular those derived as embeddings from deep learning networks.
The problem we address is the cost of similarity measurement. This is problematic for two reasons. First, large data will not fit in the fastest memory.  Second, as well as the consequences of higher memory use, the inherent cost of the comparison is high.
The notion of *quantisation* addresses these issues via smaller data representations. However with some quantisation mechanisms the cost of the comparison may actually increase, as the mapping to hardware instructions may be less efficient.

Here we introduce a novel 2-bit quantisation mechanism, giving a 16 times space saving over standard 32-bit floating point representations. Similarity measurements can be calculated using bitwise operations that can be optimised on most modern processors. We show the combination of space saving and speedup can give an effective improvement of over an order of magnitude in the cost of similarity calculations. We further show that in many high-dimensional data sets only a small loss of accuracy is incurred.
The technique is based on a strong geometric foundation, via a class of high-dimensional polytope which we call the Equi-Voronoi Polytope (EVP). In outline, each element of the high-dimensional space is mapped to its nearest vertex in some appropriate EVP, and the distance between vertices is used as a proxy distance between any two elements. We show how this can give a very accurate estimation of similarity, with very significant savings in both computation time and space.

Highlights
----------

- We show a simple computational mechanism which defines 2-bit and 1-bit quantisation over high-precision numeric vectors. The quantisation is based on a strong underlying theory of high-dimensional polytopes.

- We give similarity metrics over these representations. These metrics are highly amenable to hardware optimisation on modern SIMD processors, typically leading to an order of magnitude speed-up over the floating-point calculation on top of the improvement given by increased memory throughput.

- Despite their small size, the geometric basis underlying their derivation ensures a surprising degree of accuracy for the measurement of similarity.
To highlight the significance of our work, our experiments show that, in comparison with dimensionality reduction via Principal Component Analysis, our 2-bit quantisation is typically more accurate, much smaller, and much faster.

- Our abstractions seem particularly well suited to embeddings deriving from modern neural networks. In the best cases, our quantisation gives almost perfect accuracy for near-neighbour search.

- Although based on sophisticated geometry, our outcomes are simple to implement in practical terms.

Rust Code
---------

All the Rust code in this repo that was used in the experiments reported in the paper may be executed from the following three shell scripts:

    run_all_benchmarks.sh
    run_allinfosyss_experiments.sh
    run_infosys_experiments.sh

Matlab Code
----------

To appear.