cmake_minimum_required(VERSION 3.0)
project(matriz_adjacencias C CXX)

set(CMAKE_C_STANDARD 11)
SET(CMAKE_CXX_FLAGS "-g -O0 -fprofile-arcs -ftest-coverage")
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/.travis/cmake)


find_package(GTest REQUIRED)

set(SOURCES
        grafomatadjexercicio.c
        )

set(HEADERS
        grafomatadjexercicio.h
        )


enable_testing()
include(CodeCoverage)

add_executable(matriz_adjacencias main.c  ${SOURCES} ${HEADERS} )
add_executable(runUnitTests mainTest.cpp testGrafoMatrizAdj.h   ${SOURCES} ${HEADERS} )


target_link_libraries(runUnitTests GTest::GTest GTest::Main )

setup_target_for_coverage(coverage  runUnitTests  coverage)
