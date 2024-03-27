cmake_minimum_required(VERSION 3.0.0)
project(LearnOpenGL VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()

# 查找指定目录下的所有源文件，并将结果存进指定变量名
aux_source_directory(${PROJECT_SOURCE_DIR}/src SRC_LIST)
include_directories(${PROJECT_SOURCE_DIR}/include)

add_executable(LearnOpenGL ${SRC_LIST})
link_directories(${PROJECT_SOURCE_DIR}/lib)
target_link_libraries(${PROJECT_NAME} ${PROJECT_SOURCE_DIR}/lib/glfw3.dll)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
