cmake_minimum_required(VERSION 3.16)
project(port)


if(INCLUDE_AUDIO)

    add_subdirectory(base/id3lib)

endif()


if(NOT ${HAS_SYSTEM_UNAC})

    add_subdirectory(base/unac)

endif()


if(${INCLUDE_REDSHIFT})

add_subdirectory(user-generation1/redshift)

endif()

if(INCLUDE_OPENGL)

    add_subdirectory(graphics3d/glad)
    add_subdirectory(graphics3d/ktx)

endif()



if(${ARCH_LIKE})

    if(NOT ${HAS_SYSTEM_JPEG})
    add_subdirectory(imaging/port_jpeg)
    endif()
    add_subdirectory(imaging/port_jxr)
    add_subdirectory(imaging/port_openexr)
    add_subdirectory(imaging/port_openjpeg)
    add_subdirectory(imaging/port_png)
    add_subdirectory(imaging/port_rawlite)
    add_subdirectory(imaging/port_tiff4)
    add_subdirectory(imaging/port_webp)
    add_subdirectory(imaging/port_freeimage)

endif()

