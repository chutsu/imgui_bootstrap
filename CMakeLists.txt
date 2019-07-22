CMAKE_MINIMUM_REQUIRED(VERSION 3.0)
PROJECT(imgui-bootstrap)

# PACKAGES
FIND_PACKAGE(OpenGL REQUIRED)
INCLUDE_DIRECTORIES(${OPENGL_INCLUDE_DIR})

FIND_PACKAGE(assimp REQUIRED)
FIND_PACKAGE(glm REQUIRED)
FIND_PACKAGE(glfw3 REQUIRED)

INCLUDE_DIRECTORIES(dep/imgui dep/imgui/examples)
ADD_DEFINITIONS(-DIMGUI_IMPL_OPENGL_LOADER_GLAD)
ADD_LIBRARY(
  imgui
  dep/imgui/imgui.cpp
  dep/imgui/imgui_draw.cpp
  dep/imgui/imgui_demo.cpp
  dep/imgui/imgui_widgets.cpp
)
ADD_LIBRARY(
  imgui_impl
  dep/imgui/examples/imgui_impl_glfw.cpp
  dep/imgui/examples/imgui_impl_opengl3.cpp
)

LINK_DIRECTORIES(dep/glad/build)
INCLUDE_DIRECTORIES(dep/glad/include)

# EXECUTABLES
SET(IMGUI_BOOTSTRAP_LIBS
  glad
  glfw
  dl
  ${ASSIMP_LIBRARIES}
  ${OPENGL_gl_LIBRARY}
  imgui
  imgui_impl
)
ADD_EXECUTABLE(gui src/gui.cpp)
TARGET_LINK_LIBRARIES(gui ${IMGUI_BOOTSTRAP_LIBS})
