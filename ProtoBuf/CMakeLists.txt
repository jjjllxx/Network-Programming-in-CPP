set(NP_TARGET pb)

set(NP_SOURCES
    main.cpp)

find_package(Protobuf REQUIRED CONFIG)

include(${CMAKE_CURRENT_LIST_DIR}/Protos/CMakeLists.txt)

add_executable(${NP_TARGET} ${NP_SOURCES})

target_link_libraries(${NP_TARGET} PRIVATE
    protobuf::libprotobuf)
     
set_target_properties(${NP_TARGET} PROPERTIES 
    RUNTIME_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/bin")