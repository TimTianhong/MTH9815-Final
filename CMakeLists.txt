cmake_minimum_required(VERSION 3.5)
project(tradingsystem)

# Specify the C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Find the Boost library
find_package(Boost REQUIRED)
include_directories(${Boost_INCLUDE_DIRS})

# Add an executable
add_executable(main main.cpp)

# Link Boost libraries to the executable
if(Boost_FOUND)
    target_include_directories(main PRIVATE ${Boost_INCLUDE_DIRS})
    target_link_libraries(main PRIVATE ${Boost_LIBRARIES})
endif()