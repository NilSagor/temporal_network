# Research Question

The problem of data changing over time 


[22/03/2021]
How pattern recurrence or pattern stability could tackle concept drift problem in large data set which are represented by temporal networks or data that can be transformed.


~~How to tackle Concept drift problem in large data-sets, which are represented by temporal networks or data that can be transformed.~~ 


## objectives
change detection tests for graph

- mapping each graph to a numeric vector through embedding
- detect changes in stationarity through multivariate change detection


## Backgound
- identification problem of neorons in extra-cellular brain recordings based on their activity.

~~one to one correspondence between vertices over time.~~



# Hypothesis

- remove the the systematic changes to the data over time such as trends and seasonality by differentiating
- abrupt change may be a specific observations in a range or the change in the distribution of one or more input variables.
- more attention on higher weight and less attention on low weighted data.
- choosing a particular parameterize of the selected model at every time step.
- identify possible change patterns
[22/3/2021]
- when apply to adjacency or distances, how close they are 
- are they create cluster in any space [linear or multi-dimensional space]
- how much variation are there in the dimension.
- could   it possible to use multi-variate time series or other data-types.
 stationary hypothesis
- trend
- Seasonal component
- Cyclical component

- Irregular component
Irregular effects are the impact of random events such as strikes, earthquakes and sudden change in the weather. By their nature, the completely unpredicatable effect.



## Definition:
**Concept Drift:** the statistical properties of the target variable which the model is trying to predict, change over time in unforeseen ways. (wikipedia)
Relationship between inputs and outputs variables in the underlying problem over time.

**community :** a community with respect to  graphs can be defined as a subset of nodes that are densely connected to each other and loosely connected to the nodes in the other communities in the same graph.

** Community Detection:** in a large scale network such as online social network we could have millions of nodes and edges. Detecting communities in such network becomes a herculean task.

**Agglomerative methods:** llll.

**Divisive methods: ** hhh



## Experimental Design
Similarity measures
- Dynamic Time Warping
- Hidden Markov Models
- Edit Distance

Bivariate non-linear measures
- Entraining chaotic dynamics


# related work
- probabilistic modeling to detect and predict the changes considering short-time memory.
- detect the moment of change between one concept (network pattern) to the other.
- measuring dissimilarity between one snapshot of the temporal network and the next one in time.



##### Papers:
1. Temporal Network Pattern Identification by Community Modelling -nature
**Method:**  from large temporal network construct static reduced network (target network), then community detection is performed on the network and proposed a method to find out the best number of communities.


**particle competition method:**
Assume a network $G = (V, L)$
the set of nodes $v = \{ v_{1}, v_{2}, ... v_{|v|} \}$
the set of links or edge $L = \{l_{1}, l_{2}, ... l_{|L|}\}$
the weight of the link between nodes for unweighted network $V_{i}$ and $V_{j}$ or $\{0,1\}$ is $l_{(i,j)}$

At each iteration time $(t)$
* a particle selects a neighbor $v_{j}$ to visit choosing between a random walk (particle come back to visit a high dominated neighbor).
* the particle lose energy if it visits a node that is in the domain of a rival particle.
* it re-charges it energy when visiting an already dominated node by itself.
* If the particle has energy below a predefined low energy level then the particle becomes exhausted and it will be reset t a randomly selected node in the next iteration.


**Target network construction**
- First given temporal network  $G(t) = (V, L(t))$ transform into a reduced single layer network (target network) $G_{r} = (V_{r}, L_{r})$
- preserve the spatial-temporal pattern of $G(t)$
- For each state network of the original temporal network, calculate network measure for each state method using communicability, betweenness, katz centrality, PageRank metrics.
- for shortest paths connecting two nodes and also longer paths with a lower contribution communicability measures used
**cummunicability** has high computational complexity **alternative** PageRank
- sampling is done once for each segment of data that contains several time instants.


	- sampling
	For each physical node $v_{i}$, compute the standard deviation of the state network measure. here communicability measure $\sigma_{v_{i}}$
 is the standard deviation of the values $M_{v_{i}(t)}, T = 1, 2, ..., T$
 then select $P$ physical nodes with highest standard deviation to create the target
 	- temporal coding
	For each selected physical node $v_{r_{i}}$, compute the similarity of network measures of every pair of the state node  $S_{i}(t_{l}, t_{m}), i,m = 1, 2, ..., T, l\neq m$  
	then each pair of state node  say nodes $v_{r_{i}}(t_{l})$ and $v_{r_{j}}(t_{m})$ gets a weight $C_{1}S_{i}(t_{l}, t_{m})$ where $C_{1}\in [0,1]$ is a parameter to define the influence strength of temporal feature in the final target network. 
	by this way build $P$ separated networks.
	- spatial coding:
	 the similarity of network measure between every pair of spatially selected 		nodes, says nodes $v_{r_{i}}(t_{l})$ and $v_{r_{j}}(t_{m})$ is calculated $S_{ij}(t_{l}, t_{m}), i \neq j$.
	 the weight connection between $v_{r_{i}}(t_{l})$ and $v_{r_{j}}(t_{m})$ is $C_{2}S_{ij}(t_{l}, t_{m})$ where $C_{2}$  is constant characterize the the influence strength of spatial correlation in the largest network. 
- 

**Best particle**
It is important to determine the optimal number of particle $K$ for finding best division of the network into communities using particle competition. By layout the localized average domination level measure author displayed before
$$
R(k) = min\{ \frac{1}{V_{1}} \sum_{u \in N_{1}} (N_{u}^{1}(\infty)) \}
$$

First calculate the average highest domination level for the nodes occupied by each particle.
then choose the minimum of the $K$ average highest domination levels as the proposed measure $R(K)$

- if we put exactly $K$ particles in a network with $K$ communities, then each particle is expected to dominate a community and maximal domination level of the nodes $R(K)$ will be high.
- if we put more particles than number of communities, then at least one community will have more than one particle competing for dominance and as a result low value of particle of $R(K)$
- if we put less than $K$ particles in the network, the competition within the same community also happens due to the equal behavior of all particles and again $R(K)$ will be low.



3. From spatio-temporal data to chronological networks: An application to wildfire analysis
4. Complex networks reveal global pattern of extreme-rainfall teleconnections
5. The problem of concept drift: definitions and related work
6. Concept Drift Detection for Streaming Data
7. Understanding Concept Drift
8. What Is Concept Drift and How to Measure It?
9. An overview of concept drift applications
10. Learning under Concept Drift: an Overview
11. Concept Drift Detection for Streaming Data 
12. A Review on Dynamic Concept Drift
13.  Community based event detection in temporal networks
14. 

web:
[https://machinelearningmastery.com/gentle-introduction-concept-drift-machine-learning/]
https://www.moresteam.com/toolbox/design-of-experiments.cfm
https://github.com/briatte/awesome-network-analysis
