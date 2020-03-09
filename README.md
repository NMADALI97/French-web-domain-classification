# French Web Domain Classification

This repository contains the handing for the MVA master's class: ["Advanced learning for text and graph data ALTEGRAD"](http://math.ens-paris-saclay.fr/version-francaise/formations/master-mva/contenus-/advanced-learning-for-text-and-graph-data-239506.kjsp?RH=1242430202531) 


The goal of this challenge is to solve a web domain classification problem.  You are given a subgraphof the French web graph where nodes correspond to domains.  A directed edge between two nodesindicates that there is a hyperlink from at least one page of the source domain to at least one page ofthe target domain.  Furthermore, your are provided with the text extracted from all the pages of eachdomain.   A  subset  of  these  domains  were  manually  classified  into  8  categories  and  split  between  atraining set and a test set.  Your task is to predict the categories to which the domains of the test setbelong.

Using this implementation we have been ranked 3th among 45 teams (team up to 3 people) on both the public and the private leaderboard.

This work aims to systematically evaluate recent advanced graph embedding techniques . we evaluate 11 representative graph embedding methods selected from different categories:
- 5 matrix factorization-based: Laplacian Eigenmap, SVD, Graph Factorization, HOPE, GraRep
- 3 random walk-based: DeepWalk, node2vec, struc2vec
- 3 neural network-based: LINE, SDNE, GAE

The code can also be applied to graphs in other domains (e.g., social networks, citation networks).

## 2. Pipeline
![alt text](img/pipeline.png "Pipeline")

Fig. 1: Pipeline for applying graph embedding methods to biomedical tasks. Low-dimensional node
            representations are
            first learned from biomedical networks by graph embedding methods and then used as features to build
            specific classifiers for different tasks. For (a) matrix factorization-based methods, they use a data
            matrix (e.g., adjacency matrix) as the input to learn embeddings through matrix factorization. For (b)
            random walk-based methods, they first generate sequences of nodes through random walks and then feed the
            sequences into the word2vec model to learn node representations. For (c)
            neural network-based methods, their architectures and inputs vary from different models.


## 3. Dataset
The dataset of French domains was generated from a large crawl of the French web that was performedby the DaSciM team.
You are given the following files:
1. edgelist.txt:  a subgraph of the French web graph.  It has28,002vertices and319,498weighted,directed edges. Nodes correspond to domain ids and there is an edge between two nodes if thereis a hyperlink from at least one page of the source domain to at least one page of the target domain.
2.text directory: for each domain, a .txt file containing the text of all the pages of the domain.  The text was extracted from the HTML source code of the pages.
3.train.csv: 2,125 labeled domain ids. One domain id and category per row. The list of categories is shown in Table 1.
4.test.csv: 560 domain ids the category of which is to be predicted. One domain id per row.
5.graph baseline.csv: output of the provided graph baseline. Submissions have to follow this exact format.


## 6. Citation

```
@article{yue2019graph,
  title={Graph Embedding on Biomedical Networks: Methods, Applications, and Evaluations},
  author={Yue, Xiang and Wang, Zhen and Huang, Jingong and Parthasarathy, Srinivasan and Moosavinasab, Soheil and Huang, Yungui and Lin, M. Simon and Zhang, Wen and Zhang, Ping and Sun, Huan},
  journal={arXiv preprint arXiv:1906.05017},
  year={2019}
}

@misc{fey2019graph,
  abstract = {We introduce PyTorch Geometric, a library for deep learning on irregularly
structured input data such as graphs, point clouds and manifolds, built upon
PyTorch. In addition to general graph data structures and processing methods,
it contains a variety of recently published methods from the domains of
relational learning and 3D data processing. PyTorch Geometric achieves high
data throughput by leveraging sparse GPU acceleration, by providing dedicated
CUDA kernels and by introducing efficient mini-batch handling for input
examples of different size. In this work, we present the library in detail and
perform a comprehensive comparative study of the implemented methods in
homogeneous evaluation scenarios.},
  added-at = {2019-03-07T13:50:54.000+0100},
  author = {Fey, Matthias and Lenssen, Jan Eric},
  biburl = {https://www.bibsonomy.org/bibtex/2179bc0e62e7cd5540555825398b484a7/bechr7},
  description = {Fast Graph Representation Learning with PyTorch Geometric},
  interhash = {47c0a3de9ec59df7c4917676da57b457},
  intrahash = {179bc0e62e7cd5540555825398b484a7},
  keywords = {dl graph},
  note = {cite arxiv:1903.02428},
  timestamp = {2019-03-07T13:50:54.000+0100},
  title = {Fast Graph Representation Learning with PyTorch Geometric},
  url = {http://arxiv.org/abs/1903.02428},
  year = 2019
}


```

