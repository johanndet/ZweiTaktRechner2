cmake_minimum_required(VERSION 3.30)

#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g -std=c++17")
set(CMAKE_CXX_STANDARD 20)
set(wxBUILD_SHARED OFF)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(zwei_takt_rechner VERSION 1.0.0 LANGUAGES CXX)

find_package(wxWidgets REQUIRED COMPONENTS net core base)
if(wxWidgets_USE_FILE) # not defined in CONFIG mode
    include(${wxWidgets_USE_FILE})
endif()
add_executable(myapp mainApp.cpp mainApp.h myframe.cpp myframe.h)
target_link_libraries(myapp ${wxWidgets_LIBRARIES})