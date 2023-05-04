cmake_minimum_required(VERSION 3.26.2)

set(project_name "clox")
set(target_sources
    
    memory.c
    scanner.c
    compiler.c
    chunk.c
    debug.c
    value.c
    main.c
    vm.c
    object.c
    

)
list(TRANSFORM target_sources PREPEND "./")

project(${project_name})

file(GLOB SRC ${target_sources})

add_executable(${project_name}.out ${SRC})

target_compile_options(${project_name}.out PRIVATE -g -fsanitize=address)
target_link_libraries(${project_name}.out PRIVATE -g -fsanitize=address)  
