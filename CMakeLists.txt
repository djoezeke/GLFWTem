cmake_minimum_required(VERSION 3.16...4.1.1 FATAL_ERROR)

project(GLFWTem VERSION 0.2.0 LANGUAGES C HOMEPAGE_URL "https://www.github.com/djoezeke/GLFWTem/")

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED On)
set(CMAKE_CXX_EXTENTIONS Off)

option(ENABLE_WARNINGS "Enable compiler warnings" OFF)

#--------------------------------------------------------------------
# Apply Microsoft C runtime library option
# This is here because it also applies to tests and examples
#--------------------------------------------------------------------
if (MSVC AND NOT USE_MSVC_RUNTIME_LIBRARY_DLL)
    set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Release>:Release>")
    set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")
endif()


add_executable("${CMAKE_PROJECT_NAME}" WIN32 MACOSX_BUNDLE)

set_property(TARGET "${CMAKE_PROJECT_NAME}" PROPERTY CXX_STANDARD 17)


# Add compiler warnings
if(ENABLE_WARNINGS)
  if(MSVC)
    set(COMPILER_WARNINGS /WX /W4 /permissive-)
  elseif(CMAKE_CXX_COMPILER_ID MATCHES "(GNU|Clang)")
    set(COMPILER_WARNINGS -Werror -Wall -Wextra -Wpedantic -Wshadow -Wconversion -Wsign-conversion)
  endif()
endif()

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)
set(BUILD_SHARED_LIBS OFF CACHE BOOL "" FORCE)

# Add the subdirectories for the libraries
add_subdirectory(vendor)

# MY_SOURCES is defined to be a list of all the source files for my game
file(GLOB_RECURSE MY_SOURCES CONFIGURE_DEPENDS "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp")

target_compile_definitions("${CMAKE_PROJECT_NAME}" PUBLIC GLFW_INCLUDE_NONE=1)

target_sources("${CMAKE_PROJECT_NAME}" PRIVATE ${MY_SOURCES})

target_include_directories("${CMAKE_PROJECT_NAME}" PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include/")

target_link_libraries("${CMAKE_PROJECT_NAME}" glm glfw glad  imgui opengl32 User32 Shell32 Gdi32)
