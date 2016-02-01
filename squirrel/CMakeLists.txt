cmake_minimum_required(VERSION 3.0)
project(squirrel)

set(INCLUDE_FILES
        ../include/sqconfig.h
        ../include/squirrel.h
        sqarray.h
        sqclosure.h
        sqfuncproto.h
        sqopcodes.h
        sqpcheader.h
        sqstring.h
        squserdata.h
        squtils.h
        )

set(SOURCE_FILES
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

add_library(squirrel ${SOURCE_FILES} ${INCLUDE_FILES})
target_include_directories(squirrel PUBLIC . ../include)