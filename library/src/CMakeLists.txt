# List source files as PRIVATE so they won't be linked twice.
target_sources(library
    PRIVATE
        # Only this CMakeLists.txt resolves this.
        ${CMAKE_CURRENT_LIST_DIR}/module1.c
)
