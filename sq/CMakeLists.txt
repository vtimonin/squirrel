cmake_minimum_required(VERSION 3.4)
project(sq)

set(squirrel_SOURCE_FILES
        sq.c
        )

add_executable(sq ${squirrel_SOURCE_FILES})
target_include_directories(sq PRIVATE ${sq_SOURCE_DIR} ${squirrel_lang_SOURCE_DIR}/include)
target_link_libraries(sq squirrel sqstdlib)