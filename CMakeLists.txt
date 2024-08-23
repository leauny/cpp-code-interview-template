cmake_minimum_required(VERSION 3.28)
project(interview)

set(CMAKE_C_STANDARD 17)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_compile_options(-O0 -Wall -Wextra)

if(CMAKE_CXX_COMPILER_ID MATCHES "GNU|Clang")
  set(SANITIZER_OPTION "undefined")
  message("Enable Sanitizer: ${SANITIZER_OPTION}")
  add_compile_options(-fsanitize=${SANITIZER_OPTION} -fno-sanitize-recover=all)
  add_link_options(-fsanitize=${SANITIZER_OPTION})
endif()

# add cpp as one execute file
file(GLOB_RECURSE src_files ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp)
foreach (src_file ${src_files})
  get_filename_component(src_file_name ${src_file} NAME_WE)
  add_executable(${src_file_name} ${src_file})
endforeach ()
