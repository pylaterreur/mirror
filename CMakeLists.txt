#  Copyright 2013 Matus Chochlik. Distributed under the Boost
#  Software License, Version 1.0. (See accompanying file
#  LICENSE_1_0.txt or copy at http://www.boost.org/LICENSE_1_0.txt)
#
cmake_minimum_required(VERSION 2.8)

project(mirror CXX)

option(MIRROR_NO_DOCS "Don't build and install the documentation" Off)

# we need C++11
if(${CMAKE_COMPILER_IS_GNUCXX})
	add_definitions(-std=c++0x)
elseif("${CMAKE_CXX_COMPILER_ID}" STREQUAL "Clang")
	add_definitions(-std=c++0x)
endif()


include_directories(include)

if(NOT MIRROR_NO_DOCS)
	add_subdirectory("doc")
endif()
add_subdirectory(example)
add_subdirectory(test)
