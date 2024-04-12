cmake_minimum_required(VERSION 3.5)
project(hello)

# Find the QtWidgets library
find_package(Qt5Widgets REQUIRED)

# Tell CMake to run moc when necessary
set(CMAKE_AUTOMOC ON)

# Add the include directories for the Qt 5 Widgets module to the compile lines.
include_directories(${Qt5Widgets_INCLUDE_DIRS})

# Use the compile definitions defined in the Qt 5 Widgets module
add_definitions(${Qt5Widgets_DEFINITIONS})

# Add compiler flags for building executables (-fPIE)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${Qt5Widgets_EXECUTABLE_COMPILE_FLAGS}")

# Add the executable
add_executable(hello main.cpp)

# Link the executable to the Qt 5 Widgets library
target_link_libraries(hello ${Qt5Widgets_LIBRARIES})
