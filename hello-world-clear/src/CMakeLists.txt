cmake_minimum_required(VERSION 2.8.4)

add_executable(hello-clear main.c)

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)

install(TARGETS hello-clear RUNTIME DESTINATION bin)
