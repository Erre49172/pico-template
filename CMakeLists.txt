cmake_minimum_required(VERSION 3.12) #min cmake version

include("misc/pico_sdk_import.cmake") #SDK include file,required

pico_sdk_init() #init SDK,required

project(TEMPLATE C CXX ASM) #change to your preffered name

#source file(s)

add_executable(${PROJECT_NAME}
    "src/main.cpp"
)

#directory for includes(headers etc)

target_include_directories(${PROJECT_NAME} PRIVATE
    "include/" 
)

#libraries to add

target_link_libraries(${PROJECT_NAME}
    pico_stdlib 
)

pico_add_extra_outputs(${PROJECT_NAME}) #generate uf2