20/07/24 14:39
Tags: [[OpenGL]]
___

# Window in GLFW for opengl

strukturer filene i
- **lib** - for alle eksterne libraries
- **resources** - for alt av bilder og ressurer som skal loades inn
- **src** - for all program kode 

- *makefile* - ligger i root av prosjektet

## MAKEFILE

```makefile
# compiler
CC = g++

# compiler flags
CFLAGS = -Wall -O3 -std=c++20 -g -pthread -Wextra

#linker flags
LDFLAGS = -lglfw -lXrandr -lXi -lXxf86vm -lpthread -ldl

SRC = src/*.cpp lib/glad/src/glad.c
TARGET = game

all: $(TARGET) run

$(TARGET): $(SRC)
	$(CC) -o $(TARGET) $(SRC) $(CFLAGS) $(LDFLAGS)

clean:
	rm -f $(TARGET) # -f force removal of file

run:
	./$(TARGET)

.PHONY all clean run

```

### glfwinit()
```c++
#include <glad/glad.h> // denne alltid først
#include <GLFW/glfw.h>

int main() {
	glfwInit();
	glfwWindowHint(GLFW_CONTEXT_VERSION_MAJOR,3);
	glfwWindowHint(GLFW_CONTEXT_VERSION_MINOR, 3);
	glfwWindowHint(GLFW_OPENGL_PROFILE, GLFW_OPENGL_CORE_PROFILE);
	
}

return 0;
```

initsialiserer glfw og setter opp hviklen opengl version som skal brukes

### GLFWwindow
```c++
GLFWwinodw* window = glfwCreateWindow(width,height,"navn",NULL,NULL);
if (window == NULL) {
	std::cout << "failed to create glfw window" std::endl;
	return -1;
}

glfwMakeContextCurrent(window);

```
setter opp selve vinduet og setter konteksten for all glfw til å være i vindu

### opengl kontekst

```c++
if(!gladLoadGLLoader((GLADloadproc)glfwProcAddress)) {
	std::cout << "failed to init GLAD" << std::endl;
	return -1;
}
```
initer glad ser om den blir loadet riktig

### frambuffer size callback
```c++
void frambuffer_size_callback(GLFWwindow* window, int,width,int height) {
	(void) window;  // slipper feilmelding under compile
	glViewport(0,0,width,height);
}

// denne skal stå under glad init
glfwSetFramebufferSizeCallback(window,framebuffer_size_callback);


```
setter opp et vindu i for opengl i glfw. Kan være mindre enn glfw winduet

### input 
```c++
void processInput(GLFWwindow *window) {
	if(glfwGetKey(window,GLFW_KEY_ESCAPE) == GLFW_PRESS)
		glfwSetWindowShouldClose(window,true);
}
```
enum for alle knapper, her vil escape lukke vinduet og avslutte **main loop**

## MAIN LOOP for rendering
```c++
while(!glfwWindowShouldClose(window)) {
	// input
	processInput(window);

	// rendering av figurer skjer her
	glClearColor(0.2f,0.3f,0.3f,1.0f); // rgba
	glClear(GL_COLOR_BUFFER_BIT);

	glfwSwapBuffers(window); 
	glfwPollEvents();
}

glfwTerminate();  // husk denne for å cleane opp glfw resursser

return 0;

```


# Referanse
https://learnopengl.com/Getting-started/Hello-Window
