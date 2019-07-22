GLAD_SRC_DIR=$(PWD)/glad/src
GLAD_INC_DIR=$(PWD)/glad/include
GLAD_BLD_DIR=$(PWD)/glad/build
LIBGLAD=$(GLAD_BLD_DIR)/libglad.a
ASSIMP=$(PWD)/assimp
GLFW=$(PWD)/glfw
GLM=$(PWD)/glm
STB=$(PWD)/stb
IMGUI=$(PWD)/imgui

all: $(LIBGLAD) $(ASSIMP) $(GLFW) $(GLM) $(STB) $(IMGUI)

clean:
	@rm -rf build
	@rm -rf glad

glad:
	@pip install glad
	@mkdir -p glad
	@mkdir -p glad/build
	@glad --quiet --generator c --out glad

$(LIBGLAD): glad
	@g++ -I$(GLAD_INC_DIR) \
		-c $(GLAD_SRC_DIR)/glad.c \
		-o $(GLAD_BLD_DIR)/glad.o; \
	ar rs $(GLAD_BLD_DIR)/libglad.a $(GLAD_BLD_DIR)/glad.o

$(ASSIMP):
	git clone https://github.com/assimp/assimp

$(GLFW):
	git clone https://github.com/glfw/glfw

$(GLM):
	git clone https://github.com/g-truc/glm

$(STB):
	git clone https://github.com/nothings/stb

$(IMGUI):
	git clone https://github.com/ocornut/imgui
