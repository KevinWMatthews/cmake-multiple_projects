project(Library VERSION 1.0.0)

message(STATUS "PROJECT_SOURCE_DIR:       ${PROJECT_SOURCE_DIR}")
message(STATUS "CMAKE_CURRENT_SOURCE_DIR: ${CMAKE_CURRENT_SOURCE_DIR}")
message(STATUS "CMAKE_CURRENT_LIST_DIR:   ${CMAKE_CURRENT_LIST_DIR}")
message(STATUS "CMAKE_HOME_DIRECTORY:     ${CMAKE_HOME_DIRECTORY}")
message(STATUS "")

# Create easily-extendable source list
# It is entirely possible to add all source files here.
# This is a different method that is tailored for more complex projects.
add_library(library "")

# List header files as PUBLIC for IDE's
# List source files as PRIVATE so they won't be linked twice.
target_sources(library
    PUBLIC
        # Other CMakeLists.txt files search for this; specify the full path.
        "${CMAKE_CURRENT_LIST_DIR}/include/module1.h"
    PRIVATE
        # Only this CMakeLists.txt resolves this.
        src/module1.c
)

target_include_directories(library
    PUBLIC
        # Other CMakeLists.txt files use this; specify the full path.
        "${CMAKE_CURRENT_LIST_DIR}/include"
)

add_library(library::library ALIAS library)
