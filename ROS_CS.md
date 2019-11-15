# ROS Cheat Sheet
**Features of ROS that are hard to find from the ROS Wiki**


# Contents
1. Navigation  
    1. [Change to package directory](#roscd)
    2. [Get info about a package](#rospack)
    3. [List content of a package](#rosls)

2. Data Analysis
    1. [Topics](#rostopic)
    2. [Nodes](#rosnode)
    
3. 

## rosls
`rosls <package>` directly lists all the files inside the package.

## roscd
- `roscd <package>` changes the working directory to the package directory
- `roscd log` takes you to the log directory. This only works if some ROS program has been used in the session.

## rospack
- `rospack find <package>` prints the directory path of the package.
- `rospack depends1 <package>` prints the direct dependencies of the package

## rostopic
- `rostopic list` lists all the active topics.
- `rostopic info /<topic>`provides info about the spcecified topic
- `rostopic echo /<topic>` prints realtime data being published to the specified topic.

## rosnode
- `rosnode list` lists all active nodes.
- `rosnode info /<node>` prints info about specified node

## roswtf
- `roswtf` will examine the current package for any potential issues and print them.
