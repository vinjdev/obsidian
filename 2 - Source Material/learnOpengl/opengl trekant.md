20/07/24 15:16
Tags: [[OpenGL]]
___

# opengl trekant

alt i opengl er 3D koordinater
graphics pipeline er en prosess som gjør data om til grafikk på skjermen

## shaders
små programmer som kjøres ved hjelp av GPU

opengl graphics pipeline, abstraksjon av rendering. Ulike funksjoner som påvirker rendering
skrives i glsl. Ikke alle har default, så må lage de SELV


Viktigst **vertex shader** og **fragment shader**

### Vertex Shader

code for simpel vertex shader:
```c++
const char *vertexShaderSource = "#version 330 core\n"
	"layout (location = 0) in vec3 aPos;\n"
	"void main()\n"
	"{\n"
	"    gl_Position = vec4(aPos.x,aPos.y,aPos.z,1.0f);\n"
	"}\0";
```

Dette må compiles compiles under runtime
først gi lage et object for vertex shader som holder all informasjon om hvordan opengl skal håndtere punktene

```c++
unsigned int vertexShader; // id for vertex objektet
vertexShader = glCreateShader(GL_VERTEX_SHADER);
// sette objekte sammen med source koden for shader programmet
glShaderSource(vertexShader,1,&vertexShaderSource,NULL);
glCompileShader(vertexShader);

int success;
char infoLog[512];
glGetShaderiv(vertexShader,GL_COMPILE_STATUS,&success);
if(!success) {
	glGetShaderInfoLog(vertexShader,512,NULL,infolog);
	std::cout << "fei med vertex shader compile\n" << infoLog << std::endl;
}

```

### Fragment shader
helt lik som det over, bare bytt ut vertex med fragment

fragment shader, gjør den siste justeringen, som kalkulerer farge output av pikselen på skjermen. 

shader program som gjør dette:
```c++
const char *vertexShaderSource = "#version 330 core\n"
	"out vec4 FragColor;\n"
	"void main()\n"
	"{\n"
	"    FragColor = vec4(1.0f,0.5f,0.2f,1.0f);\n"
	"}\0";
```

## Shader program
linker sammen de ulike programmene fra graphics pipeline og kjører det som et program.

```c++
unsigned int shaderProgram; // lager id
shaderProgram = glCreateProgram(); // generer et objekt for programmet
``` 

```c++
glAttachShader(shaderProgram,vertexShader); // linker
glAttachShader(shaderProgram,fragmentShader);
glLinkProgram(shaderProgram); // linker sammen til et program

glDeleteShader(vertexShader); // trenger ikke lengre
glDeleteShader(fragmentShader);

// I RENDER LOOP
glUseProgram(shaderProgram);

```


## VERTEX INPUT, VBO og VAO

opengl trenger data for å kunne vise noe på skjermen. derfor definere noe data og hvordan opengl skal håndtere dette

tre punkter for en trekant: (opengl er i 3D)
derfor er z = 0.0f
```c++
float vertices[] = {
    -0.5f, -0.5f, 0.0f,
     0.5f, -0.5f, 0.0f,
     0.0f,  0.5f, 0.0f
};  
```
*normalized device coordinates (NDC)*
lite område mellom -1 og 1 som definere hvor på skjermen punktet skal vises. Dette er i hendhold til skjerm størrelse ved hjelp av *glViewport* fra [[Window in GLFW for opengl]]

Denne dataen lagres i VBO. Som kan håndtere mange punkter, så bedre å sende mange om gangen

### VBO
lage et sted for å lagre data for opengl å bruke i gpu. Definere hvordan opengl skal forstå minne


definere en VBO, lage objekt og gi ID
```c++
unsigned int VBO;
glGenBuffers(1,&VBO);

// si hviklen type buffer
glBindBuffer(GL_ARRAY_BUFFER,VBO);

// brukes til å si hvordan definert data skal brukes i bufferen
glBufferData(GL_ARRAY_BUFFER,sizeof(vertices),vertices,GL_STATIC_DRAW);




```

### linking vertex attributes
Må manuelt bestemme hvordan input vertex attributes skal brukes

lagret sånn
- position = 32-bit
- Ikke noe plass imellom hver vertex
- første verdi er starten på buffer

Dette viser hvordan Opengl skal håndtere vertex data
glEnablevertexattribArray. index er i layout i shader programmet
```c++
glVertexAttribPointer(0,3,GL_FLOAT,GL_FALSE,3*sizeof(float),(void*)0);

// kan være 0,1,2,3 osv. spørs hvordan shader er definert
// for farger
glEnableVertexAttribArray(0); 

```

## VAO - vertex array object
bindes til vbo, så jeg slipper å bruke samme vertex attribute pointers hele tiden (inne i render loop).

lage en vao ligner på vbo
```c++
unsigned int VAO;
glGenVertexArrays(1,&VAO); // før vbo
```

koden vil se mer sånn ut:
```c++
glBindVertexArray(VAO); // før VBO

glBindBuffer(GL_ARRAY_BUFFER,VBO);
glBufferData(GL_ARRAY_BUFFER,sizeof(vertices),vertices,GL_STATIC_DRAW);


glVertexAttribPointer(0,3,GL_FLOAT,GL_FALSE,3*sizeof(float),(void*)0);

glEnableVertexAttribArray(0); 

```

vil main loop se sånn ut:
```c++
while(!closewindow(window)) {
	input();
	
	glClearColor(farger);
	glClear(GL_COLOR_BUFFER_BIT);

	glUseProgram(shaderProgram);

	glBindVertexArray(VAO);
	glDrawArrays(GL_TRIANGLE,0,3);

	glfwSwapBuffers(window);
	glfwPollEvents();
}
```


# Referanse
https://learnopengl.com/Getting-started/Hello-Triangle

