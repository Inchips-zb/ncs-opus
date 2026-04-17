# cmake_minimum_required(VERSION 3.20.0)

# # Set default build type to Release (with optimization)
# if(NOT CMAKE_BUILD_TYPE)
#     set(CMAKE_BUILD_TYPE Release)
# endif()

# prevent compile errors and enable optimization
target_compile_options(app PRIVATE  -DHAVE_CONFIG_H)

target_sources(app PRIVATE 
    ${CMAKE_CURRENT_SOURCE_DIR}/*.c
    ${CMAKE_CURRENT_SOURCE_DIR}/celt/*.c
    ${CMAKE_CURRENT_SOURCE_DIR}/silk/*.c
    ${CMAKE_CURRENT_SOURCE_DIR}/silk/fixed/*.c
    )

target_include_directories(app PRIVATE .
    ${CMAKE_CURRENT_SOURCE_DIR}/celt
    ${CMAKE_CURRENT_SOURCE_DIR}/silk
    ${CMAKE_CURRENT_SOURCE_DIR}/silk/fixed
    )