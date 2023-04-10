"graph" is a peer-to-peer network of processes (potentially distributed across machines) that are loosely coupled using the ROS communication infrastructure.

ROS has three levels of concepts:

1. File-system level
2. The Computation Graph level
3. The Community level

**_ROS Filesystem Level_**

_Packages_ are the basic build unit in ROS. A package can contain libraries, executables, nodes, messages, services, and launch files. A package can depend on other packages. ROS builds packages into a single _workspace_.

_Metapackages_ are a special kind of package that is used to create a group of packages. A metapackage is a package that contains no code, but only declares a set of dependencies. The purpose of a metapackage is to create a group of packages that can be installed together.

_Package Manifests_ are files that contain the meta-information about a package. The package manifest is a file named `package.xml` that is in the root directory of a package. The package manifest contains information such as the package name, version, description, maintainer, license, dependencies, etc.

_Repositories_ are a collection of packages. A repository is a directory that contains a number of packages. A repository can be a local directory or a remote repository. Packages which share a VCS share the same version and can be released together using the catkin release automation tool bloom.

_Messages (msg) types_ are data structures that are used to send data between nodes. Messages are defined in `.msg` files. Messages are defined in the package that uses them. Messages are compiled into C++ code that can be included in any C++ program. The are stored in `my_package/msg/MyMessageType.msg`.

_Services (srv) types_ are data structures that are used to send a request and get a response between nodes. Services are defined in `.srv` files. Services are defined in the package that uses them. Services are compiled into C++ code that can be included in any C++ program. The are stored in `my_package/srv/MyServiceType.srv`.
