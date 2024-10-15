cmake_minimum_required(VERSION 3.20.0)
project(lecture7 VERSION 0.1.0)

include_directories(lecture7/include)

# Compilation flags
add_compile_options(-Wall -pedantic-errors)

# Add executable
add_executable(lecture7 lecture7/src/main.cpp)



add_custom_command(TARGET lecture7 POST_BUILD
    COMMAND ./lecture7 | c++filt -t
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
    COMMENT "Resolve name mangling"
    VERBATIM
)

add_custom_target(demangle ALL
    COMMAND ./lecture7 | c++filt -t
    DEPENDS lecture7
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
)

# add_custom_command(TARGET lecture7 POST_BUILD
#     COMMAND valgrind --show-error-list=yes --leak-check=full --show-leak-kinds=all --track-origins=yes ./lecture7
#     WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
#     COMMENT "Running Valgrind after building lecture7"
#     VERBATIM
# )


# add_custom_target(run_valgrind ALL
#     COMMAND valgrind --show-error-list=yes --leak-check=full --show-leak-kinds=all --track-origins=yes ./lecture7
#     DEPENDS lecture7
#     WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
# )

add_custom_command(TARGET lecture7 POST_BUILD
    COMMAND valgrind --show-error-list=yes --leak-check=full --show-leak-kinds=all --track-origins=yes ./lecture3
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
    COMMENT "Running Valgrind after building lecture3"
    VERBATIM
)


add_custom_target(run_valgrind ALL
    COMMAND valgrind --show-error-list=yes --leak-check=full --show-leak-kinds=all --track-origins=yes ./lecture3
    DEPENDS lecture3
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
)


# Set C++ standard to C++17
set_property(TARGET lecture7 PROPERTY CXX_STANDARD 17)

