cmake_minimum_required(VERSION 3.16...4.1.1 FATAL_ERROR)

set(GLFWTEM_VERSION_MAJOR 1)
set(GLFWTEM_VERSION_MINOR 1)
set(GLFWTEM_VERSION_PATCH 0)
set(GLFWTEM_VERSION_STRING "${GLFWTEM_VERSION_MAJOR}.${GLFWTEM_VERSION_MINOR}.${GLFWTEM_VERSION_PATCH}")

project(GLFWTem
    VERSION ${GLFWTEM_VERSION_STRING}
    DESCRIPTION "GLFW + OpenGL + ImGui starter template"
    HOMEPAGE_URL "https://github.com/sackeyetrue/GLFWTem"
    LANGUAGES CXX
)

if(CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
    set(GLFWTEM_IS_TOP_LEVEL ON)
else()
    set(GLFWTEM_IS_TOP_LEVEL OFF)
endif()

set(GLFWTEM_EXE_NAME "${PROJECT_NAME}" CACHE STRING "Output executable name")
set(GLFWTEM_EXE_TARGET_NAME "${GLFWTEM_EXE_NAME}")

option(GLFWTEM_ENABLE_DEBUG "Enable debug build as default" OFF)
option(GLFWTEM_PRODUCTION_BUILD "Build with production asset path" OFF)
option(GLFWTEM_BUILD_SAMPLE "Build the GLFW/OpenGL/ImGui sample" ON)
option(GLFWTEM_BUILD_TESTS "Build test targets" ${GLFWTEM_IS_TOP_LEVEL})
option(GLFWTEM_ENABLE_DOXYGEN "Build Doxygen docs" ${GLFWTEM_IS_TOP_LEVEL})
option(GLFWTEM_ENABLE_WARNINGS "Enable strict compiler warnings" ${GLFWTEM_IS_TOP_LEVEL})

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

if(MSVC AND NOT USE_MSVC_RUNTIME_LIBRARY_DLL)
    set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")
endif()

if(NOT CMAKE_BUILD_TYPE AND NOT CMAKE_CONFIGURATION_TYPES)
    if(GLFWTEM_ENABLE_DEBUG)
        set(CMAKE_BUILD_TYPE "Debug" CACHE STRING "Build type" FORCE)
    else()
        set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Build type" FORCE)
    endif()
endif()

if(NOT DEFINED CMAKE_RUNTIME_OUTPUT_DIRECTORY)
    set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}")
endif()

add_subdirectory(vendor)

if(GLFWTEM_ENABLE_DOXYGEN)
    add_subdirectory(docs)
endif()

if(GLFWTEM_BUILD_TESTS)
    include(CTest)
    enable_testing()
    add_subdirectory(tests)
endif()

if(GLFWTEM_BUILD_SAMPLE)
    add_executable(${GLFWTEM_EXE_TARGET_NAME}
        examples/opengl_glfw_imgui/main.cpp
    )

    target_compile_definitions(${GLFWTEM_EXE_TARGET_NAME} PUBLIC GLFW_INCLUDE_NONE=1)
    target_link_libraries(${GLFWTEM_EXE_TARGET_NAME} PRIVATE glm glfw glad imgui)

    if(GLFWTEM_ENABLE_WARNINGS)
        if(MSVC)
            target_compile_options(${GLFWTEM_EXE_TARGET_NAME} PRIVATE /W4 /WX /permissive-)
            target_compile_definitions(${GLFWTEM_EXE_TARGET_NAME} PRIVATE _CRT_SECURE_NO_WARNINGS)
        elseif(CMAKE_CXX_COMPILER_ID MATCHES "GNU|Clang")
            target_compile_options(${GLFWTEM_EXE_TARGET_NAME} PRIVATE
                -Wall
                -Wextra
                -Wpedantic
                -Wshadow
                -Wconversion
                -Wsign-conversion
                -Werror
            )
        endif()
    endif()

    if(GLFWTEM_PRODUCTION_BUILD)
        target_compile_definitions(${GLFWTEM_EXE_TARGET_NAME} PUBLIC
            ASSETS_PATH="./assets/"
            PRODUCTION_BUILD=1
        )
    else()
        target_compile_definitions(${GLFWTEM_EXE_TARGET_NAME} PUBLIC
            ASSETS_PATH="${CMAKE_CURRENT_SOURCE_DIR}/assets/"
            PRODUCTION_BUILD=0
        )
    endif()

    if(MSVC AND GLFWTEM_IS_TOP_LEVEL)
        set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT ${GLFWTEM_EXE_TARGET_NAME})
    endif()
endif()
