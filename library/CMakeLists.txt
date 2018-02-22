project(Library VERSION 1.0.0)

# Create easily-extendable source list
# It is entirely possible to add all source files here.
# This is a different method that is tailored for more complex projects.
add_library(library "")

# List header files as PUBLIC for IDE's
# List source files as PRIVATE so they won't be linked twice.
target_sources(library
    PUBLIC
        module1.h
    PRIVATE
        module1.c
)

target_include_directories(library
    PUBLIC
        "${CMAKE_CURRENT_SOURCE_DIRECTORY}"
)

add_library(library::library ALIAS library)
