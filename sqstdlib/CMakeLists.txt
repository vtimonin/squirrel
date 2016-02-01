cmake_minimum_required(VERSION 3.0)
project(sqstdlib)

set(INCLUDE_FILES
        ../include/sqstdsystem.h
        ../include/sqstdstring.h
        ../include/sqstdmath.h
        ../include/sqstdio.h
        ../include/sqstdblob.h
        ../include/sqstdaux.h
        sqstdblobimpl.h
        )

set(SOURCE_FILES
        sqstdblob.cpp
        sqstdio.cpp
        sqstdstream.cpp
        sqstdmath.cpp
        sqstdsystem.cpp
        sqstdstring.cpp
        sqstdaux.cpp
        sqstdrex.cpp
)

add_library(sqstdlib ${SOURCE_FILES} ${INCLUDE_FILES})
target_include_directories(sqstdlib PUBLIC . ../include )
