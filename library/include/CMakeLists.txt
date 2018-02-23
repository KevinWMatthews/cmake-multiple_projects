# List header files as PUBLIC for IDE's
target_sources(library
    PUBLIC
        # Other CMakeLists.txt files search for this; specify the full path.
        "${CMAKE_CURRENT_LIST_DIR}/module1.h"
)
