cmake_minimum_required(VERSION 3.17)
project(untitled C)

set(CMAKE_C_STANDARD 11)

add_executable(send_request main.c cJSON.h cJSON.c send_request.h send_request.c)

add_executable(server server_listener.c get_server_certs.c get_server_certs.h server_handler.c server_handler.h cJSON.c cJSON.h)

target_link_libraries(send_request PUBLIC ssl crypto)

target_link_libraries(server PUBLIC ssl crypto)