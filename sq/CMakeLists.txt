cmake_minimum_required(VERSION 3.0)
project(sq)

set(SOURCE_FILES
        sq.c
        )

add_executable(sq ${SOURCE_FILES})
target_link_libraries(sq squirrel sqstdlib)
