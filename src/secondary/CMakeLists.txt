file(GLOB_RECURSE SOURCES *.cpp)

add_library(secondary SHARED ${SOURCES})
add_library(secondary_static STATIC ${SOURCES})

target_include_directories(secondary PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_include_directories(secondary_static PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

target_link_libraries(secondary PRIVATE boost)
target_link_libraries(secondary_static PRIVATE boost)

set_target_properties(secondary PROPERTIES
  PREFIX ""
  OUTPUT_NAME "PositionCopySecondary_64"
  )
