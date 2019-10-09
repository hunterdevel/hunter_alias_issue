cmake_minimum_required(VERSION 3.2)

include(cmake/HunterGate.cmake)

HunterGate(
    URL "https://github.com/cpp-pm/hunter/archive/v0.23.218.tar.gz"
    SHA1 "9a3594a61227967fb92159339ba326701b287b19"
)

set( HUNTER_GATE_ROOT ${CMAKE_BINARY_DIR}/hunterroot )
project(test)
set( HUNTER_STATUS_DEBUG ON)
hunter_add_package( freetype )
