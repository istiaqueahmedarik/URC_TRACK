_what is package?_
=> Package in ros is a collection of files and folders that are used to create a node.

1. Create a folder. For example, in home directory create a directory name catkin_ws. This is the workspace for catkin. The name of the workspace can be anything. But it is recommended to use catkin_ws as the name of the workspace.

2. Give catkin_ws write and read permission. This can be done by using the following command:

```bash
chmod a+w catkin_ws
```

3. Change directory to catkin_ws. This can be done by using the following command:

```bash
cd catkin_ws
```

4. Create a folder name src. This is the source folder for the workspace. This can be done by using the following command:

```bash
mkdir src
```

5. Change directory to src. This can be done by using the following command:

```bash
cd src
```

6. Create a package. This can be done by using the following command:

```bash
catkin_create_pkg <package_name> [depend1] [depend2] [depend3]
```

for example:

```bash
catkin_create_pkg first rospy roscpp
```

here depend is the package on which the package depends. For example, rospy and roscpp are the packages on which the first package depends.

Now the package is created. The package is created in the src folder. The package contains the following files and folders:

- CMakeLists.txt
- package.xml
- src

We store cpp file in src and python in scripts folder. The CMakeLists.txt and package.xml files are used to build the package.

7. Create a directory name scripts inside of package. This can be done by using the following command:

```bash
cd <package_name> && mkdir scripts
```

8. Go to the catkin_ws directory. use catkin_make to build the package. This can be done by using the following command:

```bash
catkin_make
```

we will run it every time we make changes to the package.

9. Now we need to add the source to the bashrc file. This can be done by using the following command:

```bash
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
```

we add this because we need to source the package every time we open a new terminal.

11. we will write a simple python script to print hello world. This can be done by using the following command:

```bash
cd <package_name>/scripts && touch hello.py
```

now open the hello.py file and write the following code:

```python
#!/usr/bin/env python
import rospy
from std_msgs.msg import String

def hello():
    pub = rospy.Publisher('chatter', String, queue_size=10)
    rospy.init_node('talker', anonymous=True)
    rate = rospy.Rate(10) # 10hz
    while not rospy.is_shutdown():
        hello_str = "hello world %s" % rospy.get_time()
        rospy.loginfo(hello_str)
        pub.publish(hello_str)
        rate.sleep()
if __name__ == '__main__':
    try:
        hello()
    except rospy.ROSInterruptException:
        pass
```

12. If we use python, we need to modify the CMakeLists.txt file in package. This can be done by using the following command:

```bash
catkin_install_python(PROGRAMS scripts/hello.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
```

13. Now we need to build the package. This can be done by using the following command:

```bash
catkin_make
```

let's explain the code:

- In the first line, we specify the path of the python interpreter, it is called shebang.
- we import rospy and std_msgs.msg
- we create a function hello
- we create a publisher
  - syntax: pub = rospy.Publisher('chatter', String, queue_size=10)
  - chatter is the topic name
  - String is the message type
  - queue_size is the size of the queue
- we initialize the node
  - syntax: rospy.init_node('talker', anonymous=True)
  - talker is the name of the node
  - anonymous is a boolean value. If it is true, the name of the node will be unique
- we create a rate
  - syntax: rate = rospy.Rate(10) # 10hz
  - 10 is the frequency
- we create a while loop
- we create a string
- we log the string
- we publish the string
- we sleep the rate
- we call the function hello
