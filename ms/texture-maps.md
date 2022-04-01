---
description: 'By: Alice'
---

# UVs

## Beginnig with the basics

It should be common knowledge that the guns we use in game are models and these are made up of a lot of points called vertices and these are connected through edges which then come together to for individual faces.

This is a cube I made in Maya, note that for our usecase it is irrelevant wether u use Blender, Maya, 3dsmax or any other modeling tool.&#x20;

The Yellow Square is a selected Vertex.

![](<../.gitbook/assets/grafik (4) (1).png>)

The orange lines are the Edges connecting to it.

![](<../.gitbook/assets/grafik (1) (1).png>)

And this is one of the Faces.

![](<../.gitbook/assets/grafik (3) (1).png>)

As u can see this cube is completely grey, in game we want more detail and colour to it obviously so how does that work. Well, you probably know what Textures are. 2d images describing an objects colour in certain places and other properties that I will explain later.

To define how the pixels information of the 2D image gets to the 3D object the individual faces are laid out onto a flat surface. This is called its UV layout.

![](<../.gitbook/assets/grafik (15).png>)

This funny penis u see is the cubes standart uv layout, but it doeosnt have to be, u could also change it up and have multiple of the sides take up the same space to apply the same texture to those areas. Bits outside of the 1:1 space get the same texture applied to them so it’s the same but out of the way. Note that we cannot edit UVs in titanfall without editing modelfiles so go annoy libberty about that.

So with these out of the way we can talk a bit about the workflow now.

