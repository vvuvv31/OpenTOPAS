file(GLOB TOPAS_SCORING_SRC CONFIGURE_DEPENDS
    "*.hh"
    "*.cc"
)

add_library(scoring ${TOPAS_SCORING_SRC})

if (ZLIB_FOUND)
    target_compile_definitions(scoring PRIVATE TOPAS_HAS_ZLIB)
    target_link_libraries(scoring PRIVATE ZLIB::ZLIB)
endif ()
