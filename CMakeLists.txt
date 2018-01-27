cmake_minimum_required(VERSION 3.9)
project(SCR)

set(CMAKE_CXX_STANDARD 11)
SET(BOOST_ROOT "/usr/inlcude/boost")
SET(BOOST_LIBRARYDIR "/usr/inlcude/boost")


message(STATUS "start running cmakes...")

find_package(Boost)
if (Boost_FOUND)
    message(STATUS "znalazłem boost-a")
    find_package(Boost 1.57.0 COMPONENTS interprocess)
    include_directories( ${Boost_INCLUDE_DIR} )
endif()



add_executable(SCR main.cpp)
target_link_libraries(SCR rt)