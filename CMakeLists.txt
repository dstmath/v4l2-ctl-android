cmake_minimum_required(VERSION 3.18.4)
project(v4l2-ctl)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wno-missing-field-initializers -Wno-unused-parameter -Wno-sign-compare")
include_directories(./include)
include_directories(./v4l2/common)
set(v4l2-ctl_sources
        v4l2/common/codec-fwht.c
        v4l2/common/codec-v4l2-fwht.c
        v4l2/common/ir-encode.c
        v4l2/common/keymap.c
        v4l2/common/toml.c
        v4l2/common/v4l2-info.cpp
        v4l2/common/v4l2-tpg-colors.c
        v4l2/common/v4l2-tpg-core.c
        v4l2/common/v4l-stream.c
        v4l2/common/media-info.cpp

        v4l2/v4l2-ctl/v4l2-ctl-vbi.cpp
        v4l2/v4l2-ctl/v4l2-ctl-streaming.cpp
        v4l2/v4l2-ctl/v4l2-ctl.cpp
        v4l2/v4l2-ctl/v4l2-ctl-misc.cpp
        v4l2/v4l2-ctl/v4l2-ctl-subdev.cpp
        v4l2/v4l2-ctl/v4l2-ctl-selection.cpp
        v4l2/v4l2-ctl/v4l2-ctl-common.cpp
        v4l2/v4l2-ctl/v4l2-ctl-sdr.cpp
        v4l2/v4l2-ctl/v4l2-ctl-modes.cpp
        v4l2/v4l2-ctl/v4l2-ctl-io.cpp
        v4l2/v4l2-ctl/v4l2-ctl-meta.cpp
        v4l2/v4l2-ctl/v4l2-ctl-stds.cpp
        v4l2/v4l2-ctl/v4l2-ctl-tuner.cpp
        v4l2/v4l2-ctl/v4l2-ctl-overlay.cpp
        v4l2/v4l2-ctl/v4l2-ctl-edid.cpp
        v4l2/v4l2-ctl/v4l2-ctl-vidcap.cpp
        v4l2/v4l2-ctl/v4l2-ctl-vidout.cpp
        )
add_executable(v4l2-ctl ${v4l2-ctl_sources})

target_link_options(v4l2-ctl PRIVATE -static-libstdc++)
target_compile_definitions(v4l2-ctl PUBLIC -DNO_LIBV4L2)

