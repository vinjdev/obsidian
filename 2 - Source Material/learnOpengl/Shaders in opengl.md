22/07/24 14:16
Tags: [[OpenGL]] 
___

# Shaders in opengl
Små programmer som kjører på gpu
gjør om input til output, data til grafikk
- isolert, de "snakker" ikke med hverandre


## GLSL
programmerings språk
ligner på c

```c
# version version_number -> version 330 core
in type in_var_name;
in type in_var_name;

out type out_var_name

uniform uniform name

void main() {

	something to process

	out_var_name = something we processed

}
```
type kan være vektorer eller matrices

#### layout
gjør det mulig å koble vertex data med shaderen

```c
layout (location = 0) in vec3 aPos;
```
bestemmer hvilken attrib array som skal tas i bruk for den typen

### Uniforms
Kan brukes til å sende data fra applikasjon til shaders på GPU

kan endre data menes applikasjon kjører

```
#version 330 core
out vec4 FragColor;
  
uniform vec4 ourColor; 

void main()
{
    FragColor = ourColor;
} 
```

for å endre farge på en trekant med fragment shader uniform:
```c++
float timeValue = glfwGetTime();
float greenValue = (sin(timeValue) / 2.0f) + 5.0f;
int vertexColorLocation = glGenUniformLocation(shaderProgram,"ourColor");
glUseProgram(shaderProgram);
glUniform4f(vertexColorLocation,0.0f,greenValue,0.0f,1.0f);
```
en funksjon til å hente variabel *glGenUniformLocation*
og en til å bestemme den nye:
*glUniform4f*
4 og f kommer an på data deklarasjon


sjekk nettside for å sette opp en *shader class*
# Referanse
https://learnopengl.com/Getting-started/Shaders