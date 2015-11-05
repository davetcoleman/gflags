# Gflags ROS Wrapper

## Motivation

It's broken in Ubuntu 14.04
https://github.com/gflags/gflags/issues/120

## About

https://gflags.github.io/gflags/

## Usage

In your package's package.xml:

    <build_depend>gflags</build_depend>
	
In your package's CMakeLists:

    find_package(catkin REQUIRED COMPONENTS
      gflags
    )

In your code's header:

    // Command line arguments
    #include <gflags/gflags.h>

    DEFINE_int32(mode, 2, "Mode");

In your main() function:

    google::SetVersionString("0.0.1");
    google::SetUsageMessage("Explanation of what this node does");
    google::ParseCommandLineFlags(&argc, &argv, true);

    ros::init(argc, argv, "MyNode", ros::init_options::AnonymousName);

    int mode = FLAGS_mode;
