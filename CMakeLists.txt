cmake_minimum_required(VERSION 2.8)

project(WasteWarner)

set(CMAKE_CXX_STANDARD 14) #could cause issue
set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -Wall -g")
set(CMAKE_BUILD_TYPE Debug)

#warnings at max
if (CMAKE_COMPILER_IS_GNUCC)
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall")
endif(CMAKE_COMPILER_IS_GNUCC)

if(MSVC)
  set(CMAKE_CXX_FLAGS "{CMAKE_CXX_FLAGS} /W4")
endif(MSVC)

#require wxwidgets
find_package(wxWidgets REQUIRED net gl core base)
include(${wxWidgets_USE_FILE})

include_directories(include)
add_subdirectory(src)
#add_subdirectory(tests)
