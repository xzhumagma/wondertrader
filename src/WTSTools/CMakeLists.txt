
#1. cmakelist version
cmake_minimum_required(VERSION 3.5)

#2. project name
project(WTSTools LANGUAGES CXX)
SET(CMAKE_CXX_STANDARD 17)

IF(MSVC)
ELSE(GNUCC)
	SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fPIC")
ENDIF()

SET(LIBRARY_OUTPUT_PATH  ${CMAKE_BINARY_DIR}/build_${PLATFORM}/${CMAKE_BUILD_TYPE}/libs)

#7. add source code
file(GLOB SRCS *.cpp)
file(GLOB HDRS *.h)

LIST(APPEND INCS "../WTSUtils/yamlcpp")

INCLUDE_DIRECTORIES(${INCS})
LINK_DIRECTORIES(${LNKS})

ADD_LIBRARY(WTSTools ${SRCS} ${HDRS})