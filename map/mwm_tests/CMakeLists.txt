project(mwm_tests)

set(
  SRC
  multithread_mwm_test.cpp
  mwm_foreach_test.cpp
  mwm_index_test.cpp
)

omim_add_test(${PROJECT_NAME} ${SRC})
omim_link_libraries(
  ${PROJECT_NAME}
  map
  ge0
  search
  storage
  kml
  editor
  indexer
  platform
  geometry
  coding
  base
  opening_hours
  freetype
  icu
  agg
  expat
  oauthcpp
  protobuf
  jansson
  succinct
  pugixml
  oauthcpp
  ${LIBZ}
)

link_qt5_core(${PROJECT_NAME})
link_opengl(${PROJECT_NAME})

if (PLATFORM_MAC)
  omim_link_libraries(
    ${PROJECT_NAME}
    "-framework QuartzCore"
  )
endif()
