cmake_minimum_required(VERSION 3.2)

project(bloom)

if (NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Debug)
endif ()

set(LIBBLOOMDIR ${CMAKE_CURRENT_SOURCE_DIR} CACHE INTERNAL "bloom library" FORCE)

include_directories(${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/murmur2)

set(LIBBLOOM_SOURCE
        bloom.c
        murmur2/MurmurHash2.c
        )

add_library(bloom STATIC ${LIBBLOOM_SOURCE})

#add_library(bloom-shared SHARED ${LIBBLOOM_SOURCE})
#set_target_properties(bloom-shared PROPERTIES OUTPUT_NAME bloom)

