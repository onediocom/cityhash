include (TestBigEndian)

add_library(cityhash SHARED src/city.cc)
add_library(cityhash_static STATIC src/city.cc)

TEST_BIG_ENDIAN(WORDS_BIGENDIAN)
CONFIGURE_FILE(config.h.cmake ${CMAKE_BINARY_DIR}/cityhash_config/config.h)

target_include_directories(cityhash 
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/src>
    PRIVATE ${CMAKE_BINARY_DIR}/cityhash_config
)

target_include_directories(cityhash_static 
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/src>
    PRIVATE ${CMAKE_BINARY_DIR}/cityhash_config
)
