cmake_minimum_required(VERSION 3.4)
project(sqstdlib)

set(sqstdlib_SOURCE_FILES
        sqstdblob.cpp
        sqstdio.cpp
        sqstdstream.cpp
        sqstdmath.cpp
        sqstdsystem.cpp
        sqstdstring.cpp
        sqstdaux.cpp
        sqstdrex.cpp
)

add_library(sqstdlib ${sqstdlib_SOURCE_FILES})
target_include_directories(sqstdlib PRIVATE ${sqstdlib_SOURCE_DIR} ${squirrel_lang_SOURCE_DIR}/include )
