cmake_minimum_required(VERSION 3.10)
PROJECT(squaternion VERSION "2022.08.20")

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

cmake_host_system_information(RESULT HOST QUERY HOSTNAME)
cmake_host_system_information(RESULT OSN QUERY OS_NAME)
cmake_host_system_information(RESULT OS_VERSION QUERY OS_RELEASE)
cmake_host_system_information(RESULT PROC QUERY PROCESSOR_DESCRIPTION)

message(STATUS "-------------------------------------")
message(STATUS "  Project: ${PROJECT_NAME}")
message(STATUS "  C++ ${CMAKE_CXX_STANDARD}")
message(STATUS "-------------------------------------")
message(STATUS " ${HOST}")
message(STATUS " ${OSN}: ${OS_VERSION}")
message(STATUS " ${PROC}")
message(STATUS "-------------------------------------")

add_library(${PROJECT_NAME}
    src/squaternion.cpp
)
target_include_directories(${PROJECT_NAME}
    PUBLIC
        src/
)

# Examples -----------------------------------------------------------
add_subdirectory(examples)

# Tests --------------------------------------------------------------
# option(TESTS "gecko google tests" ON)
# if(${TESTS})
#     add_subdirectory(gtests)
# endif()
