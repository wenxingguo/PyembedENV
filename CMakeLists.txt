cmake_minimum_required(VERSION 3.15)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

project(PyembedENV)

find_package(Python3 REQUIRED)
find_package(PythonLibs REQUIRED)

add_executable(PyembedENV_SingleThread PyembedENV.cpp PyembedENV_SingleThread_test.cpp)
target_include_directories(PyembedENV_SingleThread PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(PyembedENV_SingleThread PRIVATE ${PYTHON_LIBRARIES})

add_executable(PyembedENV_MultiThread PyembedENV.cpp PyembedENV_MultiThread_test.cpp)
target_include_directories(PyembedENV_MultiThread PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(PyembedENV_MultiThread PRIVATE ${PYTHON_LIBRARIES})




