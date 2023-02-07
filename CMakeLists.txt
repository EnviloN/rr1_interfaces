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
)

set(srv_files
  # Add services here
  "srv/AnglesConverter.srv"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  ${srv_files}
  DEPENDENCIES example_interfaces
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()
