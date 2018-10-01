# bitcoin-connection-studies
This repository contains some research projects on bitcoin by Weiran Lin, directed by Professor Andrew Miller. These projects try to explore the possibility to tell the topology of the bitcoin world by only passively listening on the time information of bitcoin transactions. If the adversaries could find such a method, they could "attack specific peers in order to, e.g. isolate certain peers or even partition the network"(Timing Analysis for Inferring the Topology of the Bitcoin Peer-to-Peer Network, Till Neudecker) Although there are existing methods using transaction injection, active listening requires bitcoin expenses and hence is expensive. In this project we are using the flooding information collected from the Coinscope tool to do time analysis and infer about bitcoin links. 

The verbatim graph tool aims to provide visualization for the time information collected and the link information inferred, and hence aids later verifying and improving attack models. The result is a directed graph, with a threshold of counts within a period and the number of transactions shown on the links. It is worth noticing that there are many self-loops, which may infer that some nodes are implemented differently than the standard assumes. (A sample graph can be found at sample.pdf. This graph shows possible active links )

The simulation aims to overcome the difficulty of having ground truth of topology in a P2P network with many nodes. I made this simulation from scratch, using parameters both from measurement(e.g. the frequency of transaction happening in the network) and also from protocols(e.g. the connection protocol and the exponential time delay added at each node). Later on I developed my attack model by utilizing the exponential time delay properties. By normalizing the accumlation of a huge number of random processes in this broadcast model, I tried to tell the conditional probability distribution of the number of hops that the transaction message goes through, given the time information. With such probabolity data I could calculate the most likely number of hops between to nodes and infer whether they are linked. I also validated the precision of such attacks on this model. The analysis shows that if adequate of bitcion transaction messages are passed through links, we may infer their existence at a considerably high accuracy.

More details about each project and particular usage can be found at the usage.txt within every project directory.
