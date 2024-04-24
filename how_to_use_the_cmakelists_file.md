CMakeLists file to create a library out of imgui to be added to a cpp project.

Modify identifiers to suit your needs as necessary. If you're using a different backend than opengl&glfw, change the paths in the CMakeLists.txt file to that of the needed backend implementations.

Clone this repo to a subfolder called "external" and include/link imgui into your project with:
```cmake
set(IMGUI_DIR "${EXTERNAL_DIR}/imgui")
add_subdirectory("${IMGUI_DIR}")
target_include_directories(${MAIN_TARGET} PRIVATE
  "${IMGUI_DIR}"
  "${IMGUI_DIR}/backends"
  "${IMGUI_DIR}/misc/cpp"
)
target_link_libraries(${MAIN_TARGET} PRIVATE LibImGui)
```

With `${EXTERNAL_DIR}` being the path to the "external" subdir and `${MAIN_TARGET}` being the variable containing the main target (i.e. the target that will form the executable of the project).
