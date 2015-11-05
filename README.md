# Gflags ROS Wrapper

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
    google::SetUsageMessage("Node name");
    google::ParseCommandLineFlags(&argc, &argv, true);

    int mode = FLAGS_mode;
