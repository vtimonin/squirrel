cmake_minimum_required(VERSION 3.0)
project(squirrel)

set(COMPILE_DEFINITIONS)

if (NOT DEFINED SQ_EXCLUDE_DEFAULT_MEMFUNCTIONS)
    option(SQ_EXCLUDE_DEFAULT_MEMFUNCTIONS "Exclude default memory functions" OFF)
endif ()
if (SQ_EXCLUDE_DEFAULT_MEMFUNCTIONS)
    list(APPEND COMPILE_DEFINITIONS SQ_EXCLUDE_DEFAULT_MEMFUNCTIONS=1)
endif ()

if (NOT DEFINED SQ_USE_DOUBLE)
    option(SQ_USE_DOUBLE "Use double values" OFF)
endif ()
if (SQ_USE_DOUBLE)
    list(APPEND COMPILE_DEFINITIONS SQUSEDOUBLE=1)
endif ()

if (NOT DEFINED SQ_ALIGNMENT)
    set(SQ_ALIGNMENT "" CACHE STRING "Memory alignment")
endif ()
if (SQ_ALIGNMENT)
    list(APPEND COMPILE_DEFINITIONS SQ_ALIGNMENT=${SQ_ALIGNMENT})
endif ()

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
target_compile_definitions(squirrel PUBLIC ${COMPILE_DEFINITIONS})
target_include_directories(squirrel PUBLIC . ../include)