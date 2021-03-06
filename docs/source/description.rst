Features
========

EvalNE has been designed as a pipeline of interconnected and interchangeable building blocks. This structure provides the flexibility to create different evaluation pipelines and, thus, to asses the LP accuracy of methods from node embeddings, edge embeddings or similarity scores. The main building blocks that constitute EvalNE as well as the types of methods it can evaluate are presented in the following diagram. Gray blocks represent modules provided by the library and white blocks are the user-specified methods to be evaluated. 

.. image:: diagram.png
    :width: 600px
    :alt: EvalNE diagram
    :align: center

.. note::

    The hyper-parameter tuning and evaluation setup functionalities are omitter in this diagram.

A more detailed description of the library features for the practitioner and for the methodologist are presented below. Further information can be found in our arXiv paper_.

.. _paper: https://arxiv.org/abs/1901.09691

For Methodologists
------------------

A command line interface in combination with a configuration file allow the user
to evaluate any publicly available implementation of a NE method. These
implementations can be obtained from libraries such as 
OpenNE_ or GEM_ as well as directly from the web pages of the authors e.g. 
Deepwalk_, Node2vec_, LINE_, PRUNE_, Metapath2vec_, CNE_. 

.. _OpenNE: https://github.com/thunlp/OpenNE
.. _GEM: https://github.com/palash1992/GEM
.. _Deepwalk: https://github.com/phanein/deepwalk
.. _Node2vec: https://github.com/aditya-grover/node2vec
.. _LINE: https://github.com/tangjianpku/LINE
.. _PRUNE: https://github.com/ntumslab/PRUNE
.. _Metapath2vec: https://ericdongyx.github.io/metapath2vec/m2v.html
.. _CNE: https://bitbucket.org/ghentdatascience/cne/

EvalNE also includes the following LP heuristics for both directed and
undirected networks (in and out node neighbourhoods), which can be used as
baselines:

* Random Prediction
* Common Neighbours
* Jaccard Coefficient
* Adamic Adar Index
* Preferential Attachment
* Resource Allocation Index

For Practitioners
-----------------

When used as an API, EvalNE provides functions to:

- Load and preprocess graphs
- Obtain general graph statistics
- Compute train/test/validation splits
- Generate false edges
- Evaluate link prediction from:

    - Node Embeddings
    - Edge Embeddings
    - Similarity scores (e.g. the ones given by LP heuristics)

- Provides functions that compute edge embeddings from node feature vectors:

    - Average
    - Hadamard
    - Weighted L1
    - Weighted L2

- Any sklearn binary classifier can be used as a LP algorithm
- Implements several accuracy metrics.
- Includes parameter tuning subroutines

