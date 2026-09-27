cmake_minimum_required(VERSION 3.30)
project(myapp VERSION 0.1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 26)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

if(LINUX)
    set(CMAKE_LINKER_TYPE MOLD)
endif()

find_package(CLI11 CONFIG REQUIRED)
find_package(nlohmann_json CONFIG REQUIRED)

add_executable(myapp src/main.cpp)

target_compile_options(myapp PRIVATE
    -Wall -Wextra -Wpedantic -Wconversion
    $<$<CONFIG:Debug>:-fsanitize=address,undefined -fno-omit-frame-pointer -D_GLIBCXX_ASSERTIONS>
)
target_link_options(myapp PRIVATE
    $<$<CONFIG:Debug>:-fsanitize=address,undefined>
)
target_link_libraries(myapp PRIVATE
    CLI11::CLI11
    nlohmann_json::nlohmann_json
)
