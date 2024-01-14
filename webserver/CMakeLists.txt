# CMakeList.txt : CMake project for webserver, include source and define
# project specific logic here.
#

# Add source to this project's executable.
add_executable (webserver "webserver.cpp" "webserver.hpp")

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET webserver PROPERTY CXX_STANDARD 20)
endif()

find_package(asio CONFIG REQUIRED)

target_link_libraries(webserver PRIVATE asio::asio)