cmake_minimum_required(VERSION 3.8)

project(m2020_description)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)

foreach(dir config launch mhs rover)
  install(DIRECTORY ${dir}/
    DESTINATION share/${PROJECT_NAME}/${dir})
endforeach(dir)

ament_package()
