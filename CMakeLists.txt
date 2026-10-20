cmake_minimum_required(VERSION 3.21)
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(MyBotMod VERSION 1.0.0)

file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS src/*.cpp)
add_library(${PROJECT_NAME} SHARED ${SOURCES})

find_package(Geode REQUIRED)
target_link_libraries(${PROJECT_NAME} Geode::Geode)

setup_geode_mod(${PROJECT_NAME})
