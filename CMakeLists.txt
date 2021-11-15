cmake_minimum_required(VERSION 2.8.3)
project(demo_42_ros)

# The way that 42 is written, it requires that the configuration/simulation
# project which contains the runtime files are in the same directory as the 42
# executable. We hackily install the configs directory into the icd_42_ros's
# share directory, which is where the 42 executable is installed to. There's
# not much else to do, we can make sure the package exists first with the call
# to find_package below, but otherwise it's just hacky.

find_package(icd_42_ros REQUIRED)

catkin_package()

install(
    DIRECTORY configs
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/../icd_42_ros
)
