project(libhomm3Tool)
cmake_minimum_required(VERSION 3.0.2)

include_directories(${ZLIB_INCLUDE_DIRS})
include_directories(${SDL2_INCLUDE_DIR})
include_directories(${SDL2_IMAGE_INCLUDE_DIRS})
include_directories(${Boost_INCLUDE_DIRS})

set(${project}_SRCS
	lodReader.cxx
)

set(${project}_HEADERS
	lodReader.hxx
)

add_library(homm3Tool SHARED ${${project}_SRCS} ${${project}_HEADERS})
target_link_library(homm3Tool ${ZLIB_LIBRARIES} ${SDL2_LIBRARY} ${SDL2_IMAGE_LIBRARIES} ${Boost_LIBRARIES})