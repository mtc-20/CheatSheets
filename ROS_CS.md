# ROS Cheat Sheet
**Features of ROS that are hard to find (atleast for me) from the ROS Wiki**


# Contents
1. Navigation  
    1. [Change to package directory](#roscd)
    2. [Get info about a package](#rospack)
    3. [List content of a package](#rosls)

2. Data Analysis
    1. [Topics](#rostopic)
    2. [Nodes](#rosnode)
    3. [Publishers](#rosbag)
    
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

## rosbag
- rosbag lets you record all the publusher(s) and data being published and then played back later as required.
- `rosbag record -a` records all publishers in a session. The file is automatically saved with a timestamp and the .bag suffix, when you exit
- `rosbag info <bagfile_name>` prints details about the saved bag file
- `rosbag play <bagfile_name> -d -r` replays the publishers immmediately. -d specifies the waiting interval between publishers, -r specifies the rate of the publishers
- `rosbag record -O <subset_bagfile>.bag <topic_1> <topic_n>` saves only the specified pubslishers as a subset bagfile; `-O` or `--output-name` 
Alternatively
`rosbag record -o <subset_bagfile> <topic_1> <topic_n>` saves the subset bag file with a timestamp and the specified subset_bagfile name in the prefix, where `-o` or `--output-prefix`

---
## TO-DO List
- [x] rosbag
