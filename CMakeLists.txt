cmake_minimum_required(VERSION 3.17)
project(matriz_adjacencias C CXX)

set(CMAKE_C_STANDARD 11)

find_package(GTest REQUIRED)

set(SOURCES
        grafomatadjexercicio.c
        )

set(HEADERS
        grafomatadjexercicio.h
        )




add_executable(matriz_adjacencias main.c  ${SOURCES} ${HEADERS} )
add_executable(runUnitTests mainTest.cpp testGrafoMatrizAdj.h   ${SOURCES} ${HEADERS} )

target_link_libraries(runUnitTests GTest::GTest GTest::Main)

