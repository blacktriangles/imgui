################################################################################
# ROOK                                                                         #
#   (c) 2018 blacktriangles. All Rights Reserved.                              #
#   Howard N Smith <howard@blacktriangles.com>                                 #
################################################################################

include_directories(
        examples/libs/gl3w
        examples/libs/glfw/include
    )

#
# ##############################################################################
#

add_library(
        imgui
        STATIC
            imgui_draw.cpp
            imgui.cpp
    )

#
# ##############################################################################
#

add_executable( imgui_demo
        imgui_demo.cpp
        examples/libs/gl3w/GL/gl3w.c
        examples/opengl3_example/imgui_impl_glfw_gl3.cpp
        examples/opengl3_example/main.cpp
    )

target_link_libraries( imgui_demo imgui glfw ${OPENGL_LIBRARIES} )
