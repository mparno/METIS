# Add this directory for internal users.
include_directories(.)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../include)

# Find sources.
file(GLOB metis_sources *.c)

# Build libmetis.
add_library(metis ${METIS_LIBRARY_TYPE} ${metis_sources})

if(METIS_INSTALL)
  install(TARGETS metis
    LIBRARY DESTINATION lib
    RUNTIME DESTINATION lib
    ARCHIVE DESTINATION lib)
endif()
