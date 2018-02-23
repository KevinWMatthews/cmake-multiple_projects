project(Project2 VERSION 1.0.0)

add_executable(project2 main.c)

target_link_libraries(project2
    PRIVATE
        library::library
)
