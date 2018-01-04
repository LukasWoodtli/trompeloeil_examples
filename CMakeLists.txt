cmake_minimum_required(VERSION 3.0.0)

project(TrompeloeilExamples)

set(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_COLOR_MAKEFILE   ON)

if(APPLE AND CMAKE_CXX_COMPILER_ID MATCHES Clang)
	# See https://stackoverflow.com/questions/16655820/clang-mac-os-x-c11-linker-issue/16656234#16656234
	set(CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS} "-W -Wall -Wextra  -Werror -std=c++14 -stdlib=libc++ -D'_LIBCPP_EXTERN_TEMPLATE(...)='")
else()
set(CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS} "-W -Wall -Wextra  -Werror -std=c++14")
endif()

enable_testing()

include_directories(.)

add_executable(trompeloeil_examples trompeloeil_examples.cpp)
add_test(trompeloeil_examples trompeloeil_examples)
