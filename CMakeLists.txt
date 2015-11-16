# --------------------------------------------------------------
#  SRBA project
#  See docs online: https://github.com/MRPT/srba
# --------------------------------------------------------------
# Root CMake script
cmake_minimum_required(VERSION 2.8.3)
project(srba)

find_package(catkin REQUIRED)
find_package(MRPT REQUIRED base gui graphs graphslam)

catkin_package(
    INCLUDE_DIRS include
    )
include_directories(include ${catkin_INCLUDE_DIRS} ${MRPT_INCLUDE_DIRS})

add_executable(graph_slam_se2 examples/cpp/tutorial-srba-relative-graph-slam-se2.cpp)
target_link_libraries(graph_slam_se2 ${MRPT_LIBS})
add_executable(recover_global_map examples/cpp/tutorial-srba-how-to-recover-global-map.cpp)
target_link_libraries(recover_global_map ${MRPT_LIBS})

install(DIRECTORY include/ DESTINATION include)
