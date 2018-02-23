project(Library VERSION 1.0.0)

# Create easily-extendable source list
# It is entirely possible to add all source files here.
# This is a different method that is tailored for more complex projects.
add_library(library "")

# Extend the list of target sources here if need be
#target_sources(library
#    PUBLIC
#    PRIVATE
#)

# Specify source in subdirectores (pretend that it's complicated)
include(include/CMakeLists.txt)
include(src/CMakeLists.txt)

target_include_directories(library
    PUBLIC
        # Other CMakeLists.txt files use this; specify the full path.
        "${CMAKE_CURRENT_LIST_DIR}/include"
)

add_library(library::library ALIAS library)
