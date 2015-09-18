cmake_minimum_required(VERSION 3.0)

project(stb)

# stb_image shared library - combines all the stb_image*.h headers
# into one shraed library

add_library(stb_image SHARED
  stb_image.c)

if(NOT MSVC)
  target_compile_options(stb_image
    PRIVATE -Wno-unused-value)
endif()

install(TARGETS stb_image
  LIBRARY DESTINATION lib
  RUNTIME DESTINATION lib)

install(FILES stb_image.h stb_image_resize.h stb_image_write.h DESTINATION include)

# other shared lib targets (based on other stb single-header libs)
# could be added in the future
