cmake_minimum_required(VERSION 3.0 FATAL_ERROR)
project(MRM LANGUAGES CXX)

include(../../build/BuildDefaults.cmake)

add_subdirectory("src")
add_subdirectory("test")

if(MRM AND MRM_STANDALONE_APP)
    add_subdirectory("MRMHandlerProxy")
    add_subdirectory("MRMApp")
elseif (MRM)
    add_subdirectory("MRMHandler")
endif()