22/07/24 18:22
Tags: [[OpenGL]]
___

# Load sprites in Opengl (textures)
for å få til dette må man definere de punktene bildet skal ligge i. så det må inn i vertcies arrayen

texture koordinater er inne i trekanten så man de vil se sånn her ut:
```c++
float texCoords[] = {
    0.0f, 0.0f,  // lower-left corner  
    1.0f, 0.0f,  // lower-right corner
    0.5f, 1.0f   // top-center corner
};
```


## texture wrapping
hva skjer hvis vi går ut av trekanten
(0,0) og (1,1)
velge mellom:
så opengl vet hva som skal skje med bildet
```c++
GL_REPEAT // default
GL_MIRRORED_REPEAT // samme som over bare speiler
GL_CLAMP_TO_EDGE // gets strechted at border
GL_CLAMP_TO_BORDER // gets a specified border color
```
![[Pasted image 20240724161916.png]]

denne brukes i texture parameter funksjon
brukes på begge aksene x og y (s,t)

*glTexParametri()*
```c++
glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_WRAP_S, GL_MIRRORED_REPEAT);
glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_WRAP_T, GL_MIRRORED_REPEAT);
```
først vise at vi bruker 2D texture
så bestemmer s og t aksene som er x og y
og deretter bestemme **texture wrapping**

## Texture filtering (optional)
har litt og si med tanke på bilde resulasjon. bildet som Er for lite eller for stort kan vi velge hva som skjer med pixelene.

![[Pasted image 20240729105204.png]]
gl nearest ser man tydligere hver pixel
gl linaar bruker mer smooth måtte å vise pixelen

##### magnifying og minifying
hvordan bildet blir behandlet nå downscaled eller upscaled

```c++
glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_MIN_FILTER, GL_NEAREST);
glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_MAG_FILTER, GL_LINEAR);
```
## Mipmaps
flere textures som blir brukt på en gang, hvor noen er nærme andre er langt unna, kan mipmaps være bra. Fragment shaderen kan få problemer hvis for mange, siden det er forskjellige lys nivåer som den må forholde seg til.

mipmaps vil generere bilder som er mindre enn det orginale bildet

**IKKE NOE POENG** og sette på *magnifying*, fordi mipmaps bilr downscaled

## STB image loader
en header file, som tar seg av bilde opplastning. laste ned å skrive dette
'#define' basiclly omgjør .h filen til en .cpp fil
```c++
#define STB_IMAGE_IMPLEMENTATION
#include "stb_image.h"
```
loade inn bilde sånn
```c++
int width, height, nrChannels;
unsigned char *data = stbi_load("container.jpg", &width, &height, &nrChannels, 0);
```
trenger width, height og hvor mange farge kanaler som for å generere et bilde

## Genereting a texture
samme som før med opengl objects
```c++
unsigned int texture;
glGenTextures(1, &texture);  
glBindTexture(GL_TEXTURE_2D,texture);
```

textures blir loaded med dette, kan putte inn i en if else for å forsikre at data er loaded riktig
```c++
glTexImage2D(GL_TEXTURE_2D, 0, GL_RGB, width, height, 0, GL_RGB, GL_UNSIGNED_BYTE, data);
glGenerateMipmap(GL_TEXTURE_2D);
```

```c++
if (data)
{
    glTexImage2D(GL_TEXTURE_2D, 0, GL_RGB, width, height, 0, GL_RGB, GL_UNSIGNED_BYTE, data);
    glGenerateMipmap(GL_TEXTURE_2D);
}
else
{
    std::cout << "Failed to load texture" << std::endl;
}
```

## oppdatere vertex punktene
```c++
float vertices[] = {
    // positions          // colors           // texture coords
     0.5f,  0.5f, 0.0f,   1.0f, 0.0f, 0.0f,   1.0f, 1.0f,   // top right
     0.5f, -0.5f, 0.0f,   0.0f, 1.0f, 0.0f,   1.0f, 0.0f,   // bottom right
    -0.5f, -0.5f, 0.0f,   0.0f, 0.0f, 1.0f,   0.0f, 0.0f,   // bottom left
    -0.5f,  0.5f, 0.0f,   1.0f, 1.0f, 0.0f,   0.0f, 1.0f    // top left 
};
```

legge til en tredje data kolone som inneholder hvor texturen skal ligge. dette er i forhold til figuren. 1.0f er intil start punktet

vi har også endret vertex attributen, så må vise det nye formatet
![[Pasted image 20240729141302.png]]

```c++
glVertexAttribPointer(2, 2, GL_FLOAT, GL_FALSE, 8 * sizeof(float), (void*)(6 * sizeof(float)));
glEnableVertexAttribArray(2);  
```
- 2 er i layout 2 i vertex shader
- 2 fordi det bare er 2 punkter per punkt
- float
- trenger ikke å clampe
- totalt 8 punkter per vertex
- starter på den 6 (der S står over i bildet), offset

## Shader

```c

#version 330 core
layout (location = 0) in vec3 aPos;
layout (location = 1) in vec3 aColor;
layout (location = 2) in vec2 aTexCoord;

out vec3 ourColor;
out vec2 TexCoord;

void main()
{
    gl_Position = vec4(aPos, 1.0);
    ourColor = aColor;
    TexCoord = aTexCoord;
}
```

```c
#version 330 core
out vec4 FragColor;
  
in vec3 ourColor;
in vec2 TexCoord;

uniform sampler2D ourTexture;

void main()
{
    FragColor = texture(ourTexture, TexCoord);
}
```

## Bind texture in render loop
```c++
glBindtexture(GL_TEXTURE_2D,texture);
glBindVertexArray(VAO);
glDrawElements(GL_TRIANGLES,6,GL_UNSIGNED_INT,0);
```





# Referanse
https://learnopengl.com/Getting-started/Textures