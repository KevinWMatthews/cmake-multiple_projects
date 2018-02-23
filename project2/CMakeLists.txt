project(Project2 VERSION 1.0.0)

message(STATUS "PROJECT_SOURCE_DIR:       ${PROJECT_SOURCE_DIR}")
message(STATUS "CMAKE_CURRENT_SOURCE_DIR: ${CMAKE_CURRENT_SOURCE_DIR}")
message(STATUS "CMAKE_CURRENT_LIST_DIR:   ${CMAKE_CURRENT_LIST_DIR}")
message(STATUS "CMAKE_HOME_DIRECTORY:     ${CMAKE_HOME_DIRECTORY}")
message(STATUS "")

add_executable(project2 main.c)

target_link_libraries(project2
    PRIVATE
        library::library
)
