cmake_minimum_required(VERSION 3.14)
project(cbs)

IF(NOT CMAKE_BUILD_TYPE)
    SET(CMAKE_BUILD_TYPE "RELEASE")
ENDIF()

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories("inc")
file(GLOB SOURCES "src/*.cpp")
add_executable(cbs ${SOURCES})

# Find Boost
find_package(Boost REQUIRED COMPONENTS program_options)
include_directories( ${Boost_INCLUDE_DIRS} )
target_link_libraries(cbs ${Boost_LIBRARIES})
