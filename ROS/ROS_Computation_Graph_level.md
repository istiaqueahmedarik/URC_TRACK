##ROS Computation Graph Level

It is a peer-to-peer network of processes (potentially distributed across machines) that are loosely coupled using the ROS communication infrastructure.

**Nodes** are the basic computational units in ROS. A node is an executable that uses ROS to communicate with other nodes. Nodes can publish data to a topic as well as subscribe to a topic to receive data. A node can also provide and call a service to get data from and send data to other nodes. A ROS node is written with the use of a ROS client library such that roscpp or rospy.

**Master** is a name service for ROS. It keeps track of all the topics, services, and parameters that are available in the system. It also keeps track of which nodes are publishing and subscribing to which topics and which nodes are providing and using which services.

**Parameter Server** is a centralized server that stores parameters. Parameters are configuration variables that can be set and retrieved at runtime.

**Message** is a data structure that is used to send data between nodes. Messages are defined in `.msg` files. Messages are defined in the package that uses them. Messages are compiled into C++ code that can be included in any C++ program. The are stored in `my_package/msg/MyMessageType.msg`.

**Topics**
_Messages are routed via a transport system with publish/subscribe semantics. The transport system is responsible for routing messages from publishers to subscribers. The transport system is also responsible for ensuring that messages are delivered reliably, even if that means re-sending messages._
_A node sends out a message by publishing it on a topic. A node receives a message by subscribing to a topic. A topic is a name that nodes use to register as publishers or subscribers._
_A topic is a name that is used to identify the content of the messages being sent on it._
_There may be multiple publishers and subscribers for a given topic and a node may publish or subscribe to multiple topics. In general, publishers and subscribers are not aware of each others' existence._
_The idea is to decouple the production of information from its consumption.This means that a node that publishes data does not need to know anything about the nodes that are subscribing to that data. Similarly, a node that subscribes to data does not need to know anything about the nodes that are publishing that data._
_let's take a real-life analogy. Imagine a news agency that publishes news. Now here is the interesting part. The news agency can publish the news on a topic called "news". Similarly, the people who are reading the news can subscribe to the topic called "news". The news agency does not need to know anything about the people who are reading the news and the people who are reading the news do not need to know anything about the news agency. This is the idea behind the publish/subscribe model._

**Services**
_Services are a request/response paradigm. A node sends a request to a service and waits for a response. A node provides a service by responding to requests._

**Bags**
_Bags are a way to record data from topics and play them back later. They are useful for testing and debugging. They are also useful for storing data for offline analysis._

**summary**

- Nodes are the basic computational units in ROS.
- Nodes can publish data to a topic as well as subscribe to a topic to receive data.
- A node can also provide and call a service to get data from and send data to other nodes.
- A ROS node is written with the use of a ROS client library such that roscpp or rospy.
- The master is a name service for ROS.
- The parameter server is a centralized server that stores parameters.
- Messages are data structures that are used to send data between nodes.
- Topics are a way for nodes to send messages to each other.
- Services are a request/response paradigm.
- Bags are a way to record data from topics and play them back later.

![ROS Computation Graph Level](http://ros.org/images/wiki/ROS_basic_concepts.png)

![ROS Computation Graph Level](https://3384003106-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-LiHGnU31k3UMwGKWEZa%2F-Lk39CWW6hBDIZjleHWq%2F-Lk3L5yC9rPbSgrhCCUZ%2Fros_concepts1.png?alt=media&token=b9456a58-dcc7-411d-b969-2bf0f0df6f3a)
