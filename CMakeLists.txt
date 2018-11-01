cmake_minimum_required(VERSION 2.8)

project(httpserver)

FIND_PACKAGE( Boost 1.68 COMPONENTS program_options date_time filesystem system thread REQUIRED )
INCLUDE_DIRECTORIES( ${Boost_INCLUDE_DIR} )

add_executable(${PROJECT_NAME} "main.cpp")

TARGET_LINK_LIBRARIES( ${PROJECT_NAME} LINK_PUBLIC ${Boost_LIBRARIES} )
