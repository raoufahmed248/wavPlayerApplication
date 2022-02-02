set(Main_SRCS
    src/main.cpp
)

add_executable(wavPlayer
${Main_SRCS}
)

include_directories(inc)

# Specify here the libraries this program depends on
target_link_libraries(wavPlayer
wavPlayerLibSrc
)

find_package(PkgConfig)
if (PKG_CONFIG_FOUND)
  pkg_check_modules(JACK "jack")
  if (JACK_FOUND)    
    target_link_libraries(wavPlayer ${JACK_LIBRARIES})
    add_definitions(${JACK_CFLAGS} ${JACK_CFLAGS_OTHER})
  endif()
endif()


install(TARGETS wavPlayer DESTINATION bin)
