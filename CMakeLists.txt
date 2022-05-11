cmake_minimum_required(VERSION 3.7)
project(BosmaScheduler)

if("${CMAKE_CXX_COMPILER_ID}" STREQUAL "GNU")
    add_compile_options(-fdiagnostics-color=always)
elseif("${CMAKE_CXX_COMPILER_ID}" STREQUAL "Clang")
    add_compile_options(-fcolor-diagnostics)
endif()

set(CMAKE_CXX_STANDARD 11)

# threads
set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)

add_subdirectory(third-party/cocoyaxi)

add_executable(example example.cpp)

target_include_directories(example PRIVATE
                            .
)

target_link_libraries(example 
                    Threads::Threads
                    cocoyaxi::co)