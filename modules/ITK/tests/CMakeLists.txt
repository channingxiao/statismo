set( _ITKTests
  itkStandardImageRepresenterTest
  itkStandardMeshRepresenterTest
)

foreach( _test ${_ITKTests} )
  add_executable( ${_test} ${_test}.cxx )
  target_link_libraries( ${_test} statismo_core ${ITK_LIBRARIES} )
endforeach()

add_test( NAME itkStandardImageRepresenterTest
  COMMAND itkStandardImageRepresenterTest ${statismo_SOURCE_DIR}/data
  WORKING_DIRECTORY "${TEST_WORKING_DIR}" )

add_test( NAME itkStandardMeshRepresenterTest
  COMMAND itkStandardMeshRepresenterTest ${statismo_SOURCE_DIR}/data
  WORKING_DIRECTORY "${TEST_WORKING_DIR}" )

