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


Discrete time Markov chain is sequence of random variables, known as a stochastic process. in which the value of the next variable depends only on the value of the current variable, not any variable in the past. 
For instance a machine may have two states, $A$ and $E$. when it is in state $A$, there is a 40% chance of moving to state $E$ and a 60% chance of it remaining in state $A$.when it is in state $E$, there is a 70% chance of moving to state $A$ and a 30% chance of it remaining in state $E$. The sequence of states of the machine is Markov chain. The sequence of states of the machine is a Markov chain. If we denote the chain by $X_{0}, X_{1}, X_{2}, ...$ then $X_{0}$ is the state which the machine starts in and $X_{10}$ is the random variable describing its state after 10 trasnsitions.


Random wal k on Directed Graphs
A major application of random walks on directed graphs comes from trying to establish the importance of pages on the World Wide Web. One way to do this would be to take a random walk on the web and rank pages according to their stationary probability. However, several situations occur in random walks on directed graphs that did not arise with undirected graphs. One difficulty occurs if there is a node with no out edges. In this case, the directed graph is not strongly connected and so Markov chain is not strongly connected either even though the underlying undirected graph may be connected. When the walk encounters this node the walk disappears. Another difficulty is that a node or a strongly connected component with no in edges is never reached. One way to resolve these difficulties is to introduce a random restart condition. At each step, with some probability r, jump to a node selected uniformly at random and with probability 1 − r
select an edge at random and follow it. If a node has no out edges, the value of r for that node is set to one. This has the effect of converting the graph to a strongly connected graph so that the stationary probabilities exists

The Markov Chain Monte Carlo method is a technique for sampling a multivariate probability distribution p(x), where x = (x1, x2, . . . , xd) is the set of variables. Given the probability distribution p (x), one might wish to calculate the marginal distribution
p (x1) = X x2,...,xd
p (x1, . . . , xd) or the expectation of some functionf (x)
E (f) = X x1,...,xd
f (x1, . . . , xd) p (x1, . . . , xd).
The difficulty is that both computations require a summation over an exponential number of values. If each xi can take on a value from the set {1, 2, . . . , n} of values, then there are n d possible values for x. One could compute an approximate answer by generating a sample set of values for x = (x1, . . . , xd) according to the distribution p (x1, . . . , xd).

This is done by designing a Markov chain whose stationary probabilities are exactly p(x1, x2, . . . , xd) and running the chain for a sufficiently large number of steps and averaging f over the states seen in the run. The number of steps must be large enough that we are close to the limit which is the stationary distribution. In the rest of this section, we will show that under some mild conditions, the number of steps needed grows only polynomially, though the total number of states grows exponentially with d. For ease of explanation, assume that the variables take on values from some finite set. Create a directed graph with one node corresponding to each possible value of x. A random walk on the the graph is designed so that the stationary probability of the walk is p(x). The walk is designed by specifying the probability of the transition from one node to another in such a way as to achieve the desired stationary distribution. Two common
techniques for designing the walks are the Metropolis-Hasting algorithm and Gibbs sampling. We will see that the sequence of nodes after a sufficient number of steps of the walk provides a good sample of the distribution. The number of steps the walk needs to take depends on its convergence rate to its stationary distribution. We will show that this rate is related to a natural quantity called the minimum escape probability (MEP).
We used x ∈ Rd to emphasize that our distributions are multi-variate. From a Markov chain perspective, each value x can take on is a state, i.e., a node of the graph on which 23 the random walk takes place. Henceforth, we will use the subscripts i, j, k, . . . to denote states and will use pi instead of p(x1, x2, . . . , xd) to denote the probability of the state corresponding to a given set of values for the variables. Recall that in the Markov chain terminology, nodes of the graph are called states. 
Recall the notation that p(t) is the row vector of probabilities of the random walk being at each state (node of the graph) at time t. So, p(t) has as many components as there are states and its i th component, p(t)i , is the probability of being in state i at time t. Recall the long-term (t-step) average is
a
(t) =
1
t

p
(0) + p
(1) + · · · + p
(t−1)

. (1.3)
The expected value of the function P f under the probability distribution p is E(f) = i
fipi . Our estimate of this quantity will be the average value of f at the states seen in a t step run. Call this estimate a. Clearly, the expected value of a is
E(a) = X
i
fia
(t)
i
.
The expectation here is with respect to the “coin tosses” of the algorithm, not with respect to the underlying distribution p. Letting fmax denote the maximum absolute value of f. It is easy to see that





E(a) −Xifipi





≤ fmaxX
i
|pi − a
(t)
i
| = fmax|p − a
(t)
|1 (1.4)
where the quantity |p − a(t)|1 is the l1 distance between the probability distributions p and a (t) and is often called the “total variation distance” between the distributions. We will build tools to upper bound |p − a(t)|1. Since p is the steady state distribution, the t for which |p−a(t)|1 becomes small is determined by the rate of convergence of the Markov chain to its steady state.The following proposition is often useful.
Proposition 1.9 For two probability distributions p and q, |p − q|1 = 2P
i
(pi − qi)
+ =
2
P
i
(qi − pi)
+.
The proof is left as an exercise (Exercise 1.34).
1.7.1 Time Reversibility
Definition: A Markov chain is said to be time-reversible if for the steady state probabilities π, πipij = πjpji for all i and j.
24
The phrase “time-reversible” comes from the following fact. For a time-reversible Markov
chain started in the steady state, the probability of a path (sequence of states) is the same
as its reversal. That is
πi1 pi1,i2 pi2,i3
· · · pik−1,ik = πik
pik,ik−1
pik−1,ik−2
· · · pi2,i1
.
Given only the sequence of states seen, one cannot tell if time runs forward or backward, both having the same probability. More important is the fact that time reversibility simplifies the underlying mathematics as illustrated in the following lemma. The lemma states that if a probability distribution q has the property that the probability of traversing each edge is the same in both directions, then the probability distribution must be the steady state distribution of the Markov chain. The lemma is used frequently. Lemma 1.10 In a strongly connected Markov chain with transition probabilities pij , if a
vector q with non-negative components satisfies qipij = qjpji for all i and j, then qi/
P
k
qk is the stationary probability of node i. Proof: Since the chain is strongly connected, there is a unique stationary probability
vector π satisfying the equations πP = π and P i
πi = 1. Now q/ P
k
qk satisfies these
equations since P
i
qi/
P
k
qk = 1 and for each fixed j,
P
i
qipij =
P
i
qjpji = qj
P
i
pji = qj
.
Thus q must be the steady state distribution.




Incidence matrix is a common graph representation in graph theory. it is different from Adjacency matrix which encodes the relation of vertex-vertex pairs.

In graph theory an undirected graph has two kinds of incidence matrices: unoriented and oriented.




- identification problem of neorons in extra-cellular brain recordings based on their activity.

~~one to one correspondence between vertices over time.~~

## Problem formation
 A graph $G(V,E)$ consists of a set of vertices $V$ connected by edges from the set $E$. A directed graph is a graph in which edges can be traversed in only one direction. A markov Chain is directed graph which vertices correspond to states and directed edges correspond to state trasitions. A directed path through this graph is a sequence of state transitions from one state to another. 



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
- Incidence matrix
- Block design

Bivariate non-linear measures
- Entraining chaotic dynamics
### Questions about plan to resolve
- How many factors does the design have, and are the levels of these factors fixed or random?
- Are control conditions needed, and what should they be?
- Manipulation checks; did the manipulation really work?
- What are the background variables?
- What is the sample size. How many units must be collected for the experiment to be generalisable and have enough power?
- What is the relevance of interactions between factors?
- What is the influence of delayed effects of substantive factors on outcomes?
- How do response shifts affect self-report measures?
- How feasible is repeated administration of the same measurement instruments to the same units at different occasions, with a post-test and follow-up tests?
- What about using a proxy pretest?
- Are there lurking variables?
- Should the client/patient, researcher or even the analyst of the data be blind to conditions?
- What is the feasibility of subsequent application of different conditions to the same units?
-How many of each control and noise factors should be taken into account?


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
