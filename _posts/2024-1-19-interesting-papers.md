##### Title: Cooperative Graph Neural Network
Authors: 
Ben Finkelshtein, Xingyue Huang, Michael Bronstein, ˙Ismail ˙Ilkan Ceylan <br />
Department of Computer Science <br />
University of Oxford <br />
[Paper](https://arxiv.org/pdf/2310.01267.pdf)

Standard Graph neural network updates the features/values of nodes by the method of 
message passing which basically means it updates it value based the values of all of its
neighbors. Finkelshtein et. al propose an idea of daynamic roles of nodes and updating the nodes
based on their roles. The roles can be following: <br /><br />
STANDARD: Broadcast the message to neighbors that listens and listen to the neighbors that broadcast.<br />
LISTEN: Listen to neighbors that broadcast <br />
BROADCAST: Broadcast the neighbors that listen <br />
ISOLATE: Neither listen nor broadcast, effectively isolating the node <br />

The idea is very interesting. The roles of the nodes are assigned based on the Straight-through Gumbel-softmax estimator.

