cmake_minimum_required(VERSION 2.8)
include_directories(${CMAKE_CURRENT_LIST_DIR})
link_directories(/usr/local/lib)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++0x")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS}")
add_library(common STATIC common.c client.c server.c read_write.c)

add_executable(sclient sclient.c)
target_link_libraries(sclient ssl crypto common)

add_executable(wclient2 wclient2.c)
target_link_libraries(wclient2 ssl crypto common)

add_executable(wclient wclient.c)
target_link_libraries(wclient ssl crypto common)

add_executable(wserver2 wserver2.c)
target_link_libraries(wserver2 ssl crypto common)

add_executable(wserver wserver.c)
target_link_libraries(wserver ssl crypto common)
