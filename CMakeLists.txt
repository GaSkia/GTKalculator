cmake_minimum_required(VERSION 3.17)
project(YourProjectName C)

set(CMAKE_C_STANDARD 11)

# Find GTK
find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED gtk+-3.0)

# Include GTK headers
include_directories(${GTK3_INCLUDE_DIRS})
link_directories(${GTK3_LIBRARY_DIRS})
add_definitions(${GTK3_CFLAGS_OTHER})

set(SOURCE_FILES main.c)

add_executable(GTKalculator ${SOURCE_FILES})

# Link against GTK libraries
target_link_libraries(GTKalculator ${GTK3_LIBRARIES})
