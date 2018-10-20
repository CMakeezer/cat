
add_executable(key_value-test key_value-test.cpp)
target_link_libraries(key_value-test PRIVATE cat Threads::Threads)
target_include_directories(key_value-test PRIVATE .)
if(GNU)
	target_compile_options(key_value-test PRIVATE "-O0;-Wall;-Wextra")
endif()