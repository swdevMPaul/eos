file(GLOB ABI_FILES "*.abi")
add_wast_executable(TARGET exchange
  INCLUDE_FOLDERS "${STANDARD_INCLUDE_FOLDERS}"
  LIBRARIES eosiolib
  DESTINATION_FOLDER ${CMAKE_CURRENT_BINARY_DIR}
)
configure_file("${ABI_FILES}" "${CMAKE_CURRENT_BINARY_DIR}" COPYONLY)
add_dependencies( exchange currency )
