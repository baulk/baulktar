#

add_executable(
  baulktar
  baulktar.cc
  filter.cc
  extract.cc
  baulktar.rc
  baulktar.manifest)

if(BAULKTAR_ENABLE_LTO)
  set_property(TARGET baulktar PROPERTY INTERPROCEDURAL_OPTIMIZATION TRUE)
endif()

target_include_directories(baulktar PRIVATE ../../lib/libarchive ../../vendor/bela/include)
target_compile_definitions(baulktar PRIVATE LIBARCHIVE_STATIC=1)
target_link_libraries(baulktar archive belawin)
