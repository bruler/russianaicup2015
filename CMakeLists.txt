project(RussianAICup2013)
cmake_minimum_required(VERSION 3.0.0 FATAL_ERROR)
cmake_policy(VERSION 3.4.1)

ENABLE_LANGUAGE(C)

# Find includes in corresponding build directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake")

# Instruct CMake to run moc and rrc automatically when needed
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

# Apple-specific configuration
set(APPLE_SUPPRESS_X11_WARNING ON)

# Build flags
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fvisibility=hidden -fvisibility-inlines-hidden -Wall -Wextra -Wno-unused-parameter -pedantic -std=c++14 -D_LINUX")

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
file(STRINGS "sources.list" SOURCE_FILES)

add_executable(${CMAKE_PROJECT_NAME} ${SOURCE_FILES} src/Runner.cpp)