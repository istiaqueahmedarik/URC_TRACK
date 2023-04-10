general command for using node:

```bash
rosnode list # list all nodes
rosnode ping <node_name> # check if node is running
rosnode info <node_name> # get information about node
rosnode kill <node_name> # kill node
rosnode cleanup # kill all nodes
rosnode machine <node_name> # get machine name of node

rostopic # topic related command
rostopic list # list all topics
rostopic echo <topic_name> # print message on topic
rostopic hz <topic_name> # print publishing rate of topic
rostopic type <topic_name> # print message type of topic
rostopic pub <topic_name> <msg_type> <msg_data> # publish message on topic
rostopic bw <topic_name> # print bandwidth used by topic
rostopic delay <topic_name> # print delay of topic
rostopic find <topic_name> # find topic by type
rostopic info <topic_name> # print information about topic

rosparam # parameter related command
rosparam list # list all parameters
rosparam get <param_name> # get value of parameter
rosparam set <param_name> <param_value> # set value of parameter
rosparam dump <file_name> # dump parameters to file
rosparam load <file_name> # load parameters from file
rosparam delete <param_name> # delete parameter

rossrv # service related command
rossrv list # list all services
rossrv show <service_name> # print information about service
rossrv package <service_name> # print package of service
rossrv packages # print all packages with services
rossrv md5 <service_name> # print md5 sum of service

rosmsg # message related command
rosmsg list # list all messages
rosmsg show <message_name> # print information about message
rosmsg package <message_name> # print package of message
rosmsg packages # print all packages with messages
rosmsg md5 <message_name> # print md5 sum of message

rosrun
#we use rosrun to run a node from a package
rosrun <package_name> <node_name> # run node from package



```
