cmake_minimum_required(VERSION 3.12)

project(match)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

option(ENABLE_ASAN "Enable ASAN" OFF)

if (ENABLE_ASAN)
  list(APPEND CMAKE_CXX_FLAGS -fsanitize=address)
  list(APPEND CMAKE_LINKER_FLAGS -fsanitize=address)
endif()

add_executable(match src/match.cc)
