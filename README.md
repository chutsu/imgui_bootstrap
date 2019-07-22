# imgui_bootstrap

`imgui_bootstrap` as the name suggests, this repo just bootstraps IMGUI with
GLFW and GLAD. Hopefully this will save you time in bootstrapping your imgui
projects.

# Dependencies

    assimp
    glad
    glfw
    glm
    imgui
    stb

A Makefile has been created so that you can install the above dependencies
locally within this repo.

    cd dep  # Assuming we are already at the root of imgui_bootstrap
    make  # Install dependencies to `imgui_bootstrap/dep`

# Install

    cd <PATH TO IMGUI_BOOSTRAP>
    mkdir -p build
    cd build
    cmake ..
    make
    sudo make install  # By default will install to /usr/local/lib

# LICENSE

`imgui_bootstrap` is licensed under the MIT License, see LICENSE.txt for more
information.
