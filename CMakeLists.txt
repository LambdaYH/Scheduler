cmake_minimum_required(VERSION 3.7)
project(BosmaScheduler)

set(CMAKE_CXX_STANDARD 11)

# threads
set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)

add_library(BosmaScheduler INTERFACE)

target_include_directories(BosmaScheduler INTERFACE
    "$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>"
    $<INSTALL_INTERFACE:include/BosmaScheduler>
)

add_library(scheduler ALIAS BosmaScheduler)
