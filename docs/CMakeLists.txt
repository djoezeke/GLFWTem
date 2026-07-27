find_package(Doxygen QUIET)

if(NOT DOXYGEN_FOUND)
    message(STATUS "Doxygen not found; documentation target disabled.")
    return()
endif()

set(DOXYGEN_IN "${CMAKE_CURRENT_SOURCE_DIR}/doxygen/Doxyfile.in")
set(DOXYGEN_OUT "${CMAKE_CURRENT_BINARY_DIR}/Doxyfile")

if(EXISTS "${DOXYGEN_IN}")
    configure_file(${DOXYGEN_IN} ${DOXYGEN_OUT} @ONLY)
else()
    message(STATUS "Doxygen template not found at ${DOXYGEN_IN}; documentation target disabled.")
    return()
endif()

add_custom_target(doc_doxygen
    COMMAND ${DOXYGEN_EXECUTABLE} ${DOXYGEN_OUT}
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
    COMMENT "Generating API documentation with Doxygen"
    VERBATIM
)
