add_library(cityhash STATIC src/city.cc)

target_include_directories(cityhash PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/src>
)
