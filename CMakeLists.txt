#minimum CMake version required
cmake_minimum_required(VERSION 3.15)

#Project name, version and description
project(my-discord-bot VERSION 1.0 DESCRIPTION "My Discord Bot")
 
#Add DPP to the dDps
add_subdirectory(libs/DPP)
 
#Create an Executable
add_executable(${PROJECT_NAME}
    src/main.cxx
    # your others files...
)
 
#Link Libraries
target_link_libraries(${PROJECT_NAME} dpp )
 
#Specify Include Dirs
target_include_directories(${PROJECT_NAME} PRIVATE libs/DPP/include )
 
#Set C++ Version to the latest available (20)
set_target_properties(${PROJECT_NAME} PROPERTIES CXX_STANDARD 20 CXX_STANDARD_REQUIRED ON )
