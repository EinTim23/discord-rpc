cmake_minimum_required(VERSION 3.8)
project(dicord-rpc)

set(SOURCES connection_unix.cpp connection_win.cpp discord_register_linux.cpp discord_register_win.cpp discord_rpc.cpp rpc_connection.cpp serialization.cpp)

if(APPLE)
    list(APPEND SOURCES discord_register_osx.m)
endif()

add_library(discord-rpc STATIC ${SOURCES})
set_property(TARGET discord-rpc PROPERTY CXX_STANDARD 17)