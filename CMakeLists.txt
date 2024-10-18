
project(SimpleComment)

set(SOURCES
SimpleComment.cpp
)

add_library (SimpleComment MODULE ${SOURCES})

target_link_libraries(SimpleComment utils far)

target_compile_definitions(SimpleComment PRIVATE -DWINPORT_DIRECT -DUNICODE -DFAR_DONT_USE_INTERNALS)

target_include_directories(SimpleComment PRIVATE .)
target_include_directories(SimpleComment PRIVATE ../WinPort)
target_include_directories(SimpleComment PRIVATE ../far/far2sdk)

set_target_properties(SimpleComment
    PROPERTIES
        LIBRARY_OUTPUT_DIRECTORY "${INSTALL_DIR}/Plugins/SimpleComment/plug"
        PREFIX ""
        SUFFIX ".far-plug-wide")

