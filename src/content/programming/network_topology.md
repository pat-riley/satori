#Network Topology

Network topology is the arrangement of the various elements of a computer network.

* **Physyical topology** is the placement of various components of a network, including device location and cable installation
* **logical topology** illustrates how data flows within a network, regardless of it's physical design

##Point to Point 

The simplest topology with a permanent link between two endpoints. 

##Star Network

Each network host is connected to a central hub with a point-to-point connection. In star topology every node is connected to a central node called hub or switch. The switch is the server and the peripherals are the clients. All traffic that traverses the network passes therogh the central hub. The hub acts as a signal repeater. The star topology is considered the easiest topology to design and omplement. 

An advantage of the star is that it is easy to add additional nodes. The disadvantage is that it has a central point of failure.

###Extended Star


###Distributed Star

##Ring Network

A network topology that is set up in a circular fashio in which data travels around the ring in one direction and each device on the right acts as a repeater to keep the signal strong as it travels. Each device incorporates a receiver for the incoming signal and a transmitter to send the data to the next device in the ring. The network is dependant on the abillity of the signal to travel around the ring. When a device sends data, it must travel through each device on the ring unill it reaches its destination. Every node is a critical link. 

In ring topology, there is no server computer present; all nodes work as a server and repeat the signal. The disadvantages of this topology is that if one node stops wokring, the entire network is affected or stops working.

##Mesh

The value of fully meshed networks is proportional to the exponent of the number of subscribers. Assuming that communicating groups of any two endpoints, up to and including all the endooints, is approximated by Reed's Law.

###Fully connected network
A communications network in which each of the nodes is connected to each other. In graph theory this is known as a complete graph. A fully connected network doesn't need to use switching or broadcasting. It's main disadvantage is that the number of connections grow quadratically with the number of nodes. It is extremely inpractical for large networks. A two-node network is technically a fully connected network.

###Partially Connected

Some of the nodes on the network are connected to more an one other node in the network with a point-to-point link. This makes it possible to take advatage of some of the redundancy that is provided by a physically fully connected network without the expense and complexity required for a connection between every node in the network.


##Tree

Tree topology is structed like a tree in the real world. Tree structure has a root node, intermediate nodes, and leaves. Root node is the main head node of the structure, and the leaves are the last nodes, which have no further nodes. 

The structure is arranged in hierarchical form, any nodes can have any number of child nodes.







