# glfw : window oppener
add_subdirectory(glfw)

# glad  : openGL loade
add_subdirectory(glad)

# stb_image : loading images
add_subdirectory(stb-image)

# glm : math library
add_library(glm INTERFACE)
target_include_directories(glm INTERFACE include "${CMAKE_CURRENT_SOURCE_DIR}/")

# imgui immediate mode ui
add_library(imgui)
target_sources(imgui PRIVATE
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui/imgui.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui/imgui_demo.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui/imgui_draw.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui/imgui_tables.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui/imgui_widgets.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui/backends/imgui_impl_glfw.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui/backends/imgui_impl_opengl3.cpp"
)

target_include_directories(imgui PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/imgui" "${CMAKE_CURRENT_SOURCE_DIR}/imgui/backends/")
target_link_libraries(imgui PUBLIC glfw glad)
