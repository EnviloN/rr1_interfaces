cmake_minimum_required(VERSION 3.8)
project(rr1_interfaces)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)

# Dependencies used in a custom interfaces
find_package(example_interfaces REQUIRED)

set(msg_files
  # Add messages here
  "msg/Experiment2B.msg"
  "msg/Experiment4B.msg"
  "msg/Experiment8B.msg"
  "msg/Experiment16B.msg"
  "msg/Experiment32B.msg"
  "msg/Experiment64B.msg"
  "msg/Experiment128B.msg"
  "msg/Experiment256B.msg"
  "msg/Experiment512B.msg"
  "msg/Experiment1024B.msg"
  "msg/Experiment2048B.msg"
  "msg/Experiment4096B.msg"
  "msg/Experiment8192B.msg"
  "msg/Experiment16384B.msg"
  "msg/Experiment32768B.msg"
  "msg/Experiment65536B.msg"
  "msg/Experiment131072B.msg"
  "msg/Experiment262144B.msg"
  "msg/Experiment524288B.msg"
  "msg/Experiment1048576B.msg"
  "msg/Experiment2097152B.msg"
)

set(srv_files
  # Add services here  
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  ${srv_files}
  DEPENDENCIES example_interfaces
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()
