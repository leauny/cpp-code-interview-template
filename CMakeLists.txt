cmake_minimum_required(VERSION 3.28)
project(interview)

set(CMAKE_CXX_STANDARD 17)

# add cpp as one execute file
file(GLOB_RECURSE src_files ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp)
foreach (src_file ${src_files})
  get_filename_component(src_file_name ${src_file} NAME_WE)
  add_executable(${src_file_name} ${src_file})
endforeach ()
