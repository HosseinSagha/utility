file(GLOB SOURCES CONFIGURE_DEPENDS ${CMAKE_CURRENT_LIST_DIR}/*.cpp)

get_filename_component(LIB_ID ${CMAKE_CURRENT_LIST_DIR} NAME)
add_library(${LIB_ID} STATIC ${SOURCES})

target_include_directories(${LIB_ID} INTERFACE ${CMAKE_CURRENT_LIST_DIR})
target_link_libraries(${LIB_ID} PRIVATE threadx-cpp segger-rtt)
