cmake_minimum_required(VERSION 3.0.0)
project(introToOpenCV VERSION 0.1.0)
set(TARGET_NAME "introToOpenCV")

include(CTest)
enable_testing()

find_package(OpenCV REQUIRED)

add_executable(${TARGET_NAME} main.cpp)
target_include_directories(${TARGET_NAME} PRIVATE ${OpenCV_INCLUDE_DIRS})
target_link_libraries(${TARGET_NAME} PUBLIC ${OpenCV_LIBS})

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)