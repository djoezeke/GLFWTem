cmake_minimum_required(VERSION 3.16...4.1.1 FATAL_ERROR)

#--------------------------------------------------------------------
# Project and version.
#--------------------------------------------------------------------

set (GLFWTEM_VERSION_MAJOR 1)
set (GLFWTEM_VERSION_MINOR 0)
set (GLFWTEM_VERSION_PATCH 0)
set (GLFWTEM_VERSION_STRING ${GLFWTEM_VERSION_MAJOR}.${GLFWTEM_VERSION_MINOR}.${GLFWTEM_VERSION_PATCH})

project(GLFWTem
        VERSION ${GLFWTEM_VERSION_STRING} 
        DESCRIPTION "GLFW Starter Template C/C++"
        HOMEPAGE_URL "https://github.com/djoezeke/GLFWTem"
        LANGUAGES  CXX
)

#--------------------------------------------------------------------
# Preparations depending on the specified build options  
#--------------------------------------------------------------------

if (CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
  set(GLFWTEM_IS_TOP_LEVEL ON)
else()
  set(GLFWTEM_IS_TOP_LEVEL OFF)
endif()

#--------------------------------------------------------------------
# Configure variables   
#--------------------------------------------------------------------

set(GLFWTEM_EXE_NAME ${PROJECT_NAME} CACHE STRING "Base name of executable output name")

set(GLFWTEM_EXE_TARGET_NAME  ${GLFWTEM_EXE_NAME})

option(GLFWTEM_ENABLE_DEBUG "Enable debug build" OFF)
option(GLFWTEM_PRODUCTION_BUILD "Make this a production build!" OFF)
option(GLFWTEM_BUILD_TESTS "Build the ${PROJECT_NAME} test programs" ${GLFWTEM_IS_TOP_LEVEL})
option(GLFWTEM_ENABLE_DOXYGEN "Build documentation with Doxygen." ${GLFWTEM_IS_TOP_LEVEL})
option(GLFWTEM_ENABLE_WARNING "Enable warning messages." ${GLFWTEM_IS_TOP_LEVEL})

# Set required C/C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_EXTENTIONS OFF)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

#--------------------------------------------------------------------
# Apply Microsoft C runtime library option
# This is here because it also applies to tests and examples
#--------------------------------------------------------------------
if (MSVC AND NOT USE_MSVC_RUNTIME_LIBRARY_DLL)
    set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Release>:Release>")
    set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")
endif()

if(MSVC) 
  add_compile_options(/arch:AVX2) #make sure SIMD optimizations take place
	add_compile_definitions(_CRT_SECURE_NO_WARNINGS)
endif()

#--------------------------------------------------------------------
# Configurations
#--------------------------------------------------------------------

# Default to build type "Release" unless debug is enabled
if(NOT CMAKE_BUILD_TYPE)
	if (NOT GLFWTEM_ENABLE_DEBUG)
		message(STATUS "No build type selected, default to Release")
		set(CMAKE_BUILD_TYPE "Release")
	else()
		message(STATUS "No build type selected but tests are being built, default to Debug")
		set(CMAKE_BUILD_TYPE "Debug")
	endif()
endif()

# Add compiler warnings
if(GLFWTEM_ENABLE_WARNINGS)
  if(MSVC)
    set(COMPILER_WARNINGS /WX /W4 /permissive-)
  elseif(CMAKE_CXX_COMPILER_ID MATCHES "(GNU|Clang)")
    set(COMPILER_WARNINGS -Werror -Wall -Wextra -Wpedantic -Wshadow -Wconversion -Wsign-conversion)
  endif()
endif()

# Output directories for a build tree
if(NOT DEFINED CMAKE_RUNTIME_OUTPUT_DIRECTORY)
  set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR})
endif()

#--------------------------------------------------------------------
# Add Subdirectories
#--------------------------------------------------------------------

# Build vendor libraries
add_subdirectory(vendor)

# Build the documentation   
if(GLFWTEM_ENABLE_DOXYGEN)
    add_subdirectory(docs)
endif()

# Build the test apps   
if(GLFWTEM_BUILD_TESTS)
    include(CTest)
    enable_testing()
    add_subdirectory(tests)

    # Set the unit test app project as the Visual Studio startup project
    # if the target compiler is some version of Microsoft Visual C++ and
    # if this project is the main project.
    if(MSVC AND CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
        set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT "${PROJECT_NAME}Test")
    endif()
endif()

#--------------------------------------------------------------------
# Build targets
#--------------------------------------------------------------------

include_directories("." "./include" "vendor/imgui" "vendor/glm" "vendor/glfw/include" "vendor/glad/include" "vendor/stb-image/include")

set(GLFWTEM_SOURCE_FILES "src/main.cpp")

# Add executable
add_executable("${GLFWTEM_EXE_TARGET_NAME}" "${GLFWTEM_SOURCE_FILES}")
target_compile_definitions("${GLFWTEM_EXE_TARGET_NAME}" PUBLIC GLFW_INCLUDE_NONE=1)
target_link_libraries("${GLFWTEM_EXE_TARGET_NAME}" glm glfw glad imgui)


if(GLFWTEM_PRODUCTION_BUILD)
	# setup the ASSETS_PATH macro to be in the root folder of your exe
	target_compile_definitions("${GLFWTEM_EXE_TARGET_NAME}" PUBLIC ASSETS_PATH="./assets/") 
	target_compile_definitions("${GLFWTEM_EXE_TARGET_NAME}" PUBLIC PRODUCTION_BUILD=1) 
else()
	# This is useful to get an ASSETS_PATH in your IDE during development
	target_compile_definitions("${GLFWTEM_EXE_TARGET_NAME}" PUBLIC ASSETS_PATH="${CMAKE_CURRENT_SOURCE_DIR}/assets/")
	target_compile_definitions("${GLFWTEM_EXE_TARGET_NAME}" PUBLIC PRODUCTION_BUILD=0) 
endif()
