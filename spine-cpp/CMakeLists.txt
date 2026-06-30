cmake_minimum_required(VERSION 3.10)
project(spine-cpp)

include(${CMAKE_CURRENT_LIST_DIR}/../flags.cmake)

include_directories(include)
file(GLOB INCLUDES "spine-cpp/include/**/*.h")
file(GLOB SOURCES "spine-cpp/src/**/*.cpp")

add_library(spine-cpp STATIC ${SOURCES} ${INCLUDES})
target_include_directories(spine-cpp PUBLIC spine-cpp/include)

# Install target
install(TARGETS spine-cpp DESTINATION dist/lib)
install(FILES ${INCLUDES} DESTINATION dist/include)
