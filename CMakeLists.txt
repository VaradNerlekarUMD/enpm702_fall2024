cmake_minimum_required(VERSION 3.20.0)
project(lecture8 VERSION 0.1.0)

# Compilation flags
add_compile_options(-Wall)

include_directories(lecture8/include)
# Add executable
add_executable(lecture8 
    lecture8/src/main.cpp)

<<<<<<< HEAD
<<<<<<< HEAD


add_custom_command(TARGET lecture4 POST_BUILD
    COMMAND ./lecture4 | c++filt -t
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
    COMMENT "Resolve name mangling"
    VERBATIM
)

add_custom_target(demangle ALL
    COMMAND ./lecture4 | c++filt -t
    DEPENDS lecture4
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
)

# add_custom_command(TARGET lecture4 POST_BUILD
#     COMMAND valgrind --show-error-list=yes --leak-check=full --show-leak-kinds=all --track-origins=yes ./lecture4
#     WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
#     COMMENT "Running Valgrind after building lecture4"
=======
# add_custom_command(TARGET lecture7 POST_BUILD
#     COMMAND valgrind --show-error-list=yes --leak-check=full --show-leak-kinds=all --track-origins=yes ./lecture7
#     WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
#     COMMENT "Running Valgrind after building lecture7"
>>>>>>> 478d62f97b3035b76b260b70c8fa5246c0d27275
=======
# add_custom_command(TARGET lecture8 POST_BUILD
#     COMMAND valgrind --show-error-list=yes --leak-check=full --show-leak-kinds=all --track-origins=yes ./lecture8
#     WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
#     COMMENT "Running Valgrind after building lecture8"
>>>>>>> be7e9f955c27e83c157edf8fe89bcf541edc45e5
#     VERBATIM
# )


# add_custom_target(run_valgrind ALL
<<<<<<< HEAD
<<<<<<< HEAD
#     COMMAND valgrind --show-error-list=yes --leak-check=full --show-leak-kinds=all --track-origins=yes ./lecture4
#     DEPENDS lecture4
=======
#     COMMAND valgrind --show-error-list=yes --leak-check=full --show-leak-kinds=all --track-origins=yes ./lecture7
#     DEPENDS lecture7
>>>>>>> 478d62f97b3035b76b260b70c8fa5246c0d27275
=======
#     COMMAND valgrind --show-error-list=yes --leak-check=full --show-leak-kinds=all --track-origins=yes ./lecture8
#     DEPENDS lecture8
>>>>>>> be7e9f955c27e83c157edf8fe89bcf541edc45e5
#     WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
# )

add_custom_command(TARGET lecture4 POST_BUILD
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
set_property(TARGET lecture8 PROPERTY CXX_STANDARD 17)

