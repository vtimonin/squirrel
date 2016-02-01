cmake_minimum_required(VERSION 3.4)
project(squirrel)

set(squirrel_SOURCE_FILES
        sqapi.cpp
        sqbaselib.cpp
        sqfuncstate.cpp
        sqdebug.cpp
        sqlexer.cpp
        sqobject.cpp
        sqcompiler.cpp
        sqstate.cpp
        sqtable.cpp
        sqmem.cpp
        sqvm.cpp
        sqclass.cpp
)

add_library(squirrel ${squirrel_SOURCE_FILES})
target_include_directories(squirrel PRIVATE ${squirrel_SOURCE_DIR} ${squirrel_SOURCE_DIR}/../include )
