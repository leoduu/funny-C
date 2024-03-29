cmake_minimum_required(VERSION 2.8.12)

# project name 
project(std-c)

# include directory
include_directories(${PROJECT_SOURCE_DIR}/template)
include_directories(${PROJECT_SOURCE_DIR}/vector)
include_directories(${PROJECT_SOURCE_DIR}/overload)
include_directories(${PROJECT_SOURCE_DIR}/rbtree)
include_directories(${PROJECT_SOURCE_DIR}/smart_ptr)
include_directories(${PROJECT_SOURCE_DIR}/clist)
include_directories(${PROJECT_SOURCE_DIR}/lock-free)

# add executable file
add_executable(vector   ${PROJECT_SOURCE_DIR}/vector/vector.c)
add_executable(template ${PROJECT_SOURCE_DIR}/template/template.c)
add_executable(overload ${PROJECT_SOURCE_DIR}/overload/overload.c)
add_executable(rbtree   ${PROJECT_SOURCE_DIR}/rbtree/rbtree.c)
add_executable(smart_ptr ${PROJECT_SOURCE_DIR}/smart_ptr/smart_ptr.c)
add_executable(clist ${PROJECT_SOURCE_DIR}/clist/clist.c)
add_executable(lock-free ${PROJECT_SOURCE_DIR}/lock-free/queue.c 
                        ${PROJECT_SOURCE_DIR}/lock-free/test.c
                        ${PROJECT_SOURCE_DIR}/lock-free/ringbuffer.c)

set_target_properties(lock-free PROPERTIES
                        COMPILE_FLAGS "-pthread"
                        LINK_FLAGS "-pthread")

