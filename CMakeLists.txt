cmake_minimum_required(VERSION 3.10)

# 设置项目名称和版本
project(MyMapSoft VERSION 0.0.1)

# 设置C++语言标准
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# 查找map和include目录下的所有源文件
file(GLOB_RECURSE SOURCES 
    "map/*.cpp" 
    "map/*.cxx" 
    "map/*.cc" 
    "map/*.h" 
    "include/*.h")

# 添加main.cpp到源文件列表
list(APPEND SOURCES "main.cpp")

# 编译可执行文件
add_executable(MyMapSoft ${SOURCES})

# 设置包含目录
target_include_directories(MyMapSoft PRIVATE
    "${PROJECT_SOURCE_DIR}/include"
)

# 设置可执行文件的输出路径
set_target_properties(MyMapSoft PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/release"
)
