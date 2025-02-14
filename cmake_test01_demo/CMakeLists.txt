# 指定CMake的最低版本要求为3.20.0
cmake_minimum_required(VERSION 3.20.0)
# 定义项目名称my_hello
project(my_hello)
# 设置C++标准为C++11
set(CMAKE_CXX_STANDARD 11)

# 将${PROJECT_SOURCE_DIR}/include目录添加到头文件搜索路径中
include_directories(${PROJECT_SOURCE_DIR}/include)
# 设置可执行文件的输出目录为 ${PROJECT_SOURCE_DIR}/bin
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)

# 将${PROJECT_SOURCE_DIR}/src目录下的所有源文件(如.cpp文件)添加到变量SRC_LIST中
aux_source_directory(${PROJECT_SOURCE_DIR}/src SRC_LIST)

# 定义一个可执行文件目标my_hello，并使用SRC_LIST中的源文件进行编译
add_executable(
    my_hello
    ${SRC_LIST}
)