include("config.cmake")

cmake_minimum_required(VERSION 3.0.0)
project(sdl_example VERSION 0.1.0)

include(CTest)
enable_testing()

add_executable(${PROJECT_NAME} WIN32 ${SRC_LIST})
# add_executable(${PROJECT_NAME} ${SRC_LIST})
target_compile_definitions(${PROJECT_NAME} PUBLIC ${DEF_LIST})
target_include_directories(${PROJECT_NAME} PUBLIC ${INC_PATH})
target_link_directories(${PROJECT_NAME} PUBLIC ${LIB_PATH})
target_link_libraries(${PROJECT_NAME} PUBLIC ${LIB_LIST})

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
