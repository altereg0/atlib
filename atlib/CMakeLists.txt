#####################################################################
# @lib library
#####################################################################

set( ATLIB_SRC_FILES
        src/io.cpp
        src/uart.cpp
#        src/software_uart.cpp
        )

#target_compile_options(
#        automaton
#        ATM_PLAYER_DISABLE_TONE
#)

add_avr_library(
        atlib
        ${ATLIB_SRC_FILES}
)

avr_target_include_common_directories(
        atlib PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/src
        ${CMAKE_CURRENT_SOURCE_DIR}/inc
)

set( ATLIB_TYPE_SRC_FILES
        inc/at.h
        )
add_avr_interface_library( atlib-type ${ATLIB_TYPE_SRC_FILES} )


message( STATUS "ATLIB: ${CMAKE_CURRENT_SOURCE_DIR}" )
message( ">\tCurrent build type: ${CMAKE_BUILD_TYPE}" )
