cmake_minimum_required(VERSION 2.8.4)

add_executable(hello-world-lib main.c)

include_directories(../include/hello)

find_library(HELLO_LIB NAMES hello PATHS "../lib/")
if(NOT HELLO_LIB)
    message(WARNING "hello library not found ../lib/")
endif()

find_library(HELLO_LIB NAMES hello PATHS "../../hello-world-lib/lib/")
if(NOT HELLO_LIB)
    message(WARNING "hello library not found")
else(NOT HELLO_LIB)
    message(WARNING "hello library  found " ${HELLO_LIB})
endif()

#find_library(HELLO_LIB NAMES hello PATHS "../hello-world-lib/lib/")
#if(NOT HELLO_LIB)
#    message(FATAL_ERROR "hello library not found")
#endif()

message(STATUS "Library path HELLO_LIB is " ${HELLO_LIB})

target_link_libraries(hello-world-lib ${HELLO_LIB})

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
