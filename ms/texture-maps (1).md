---
description: 'By: Alice'
---

# Texture maps

If you are planning on using maps from the base game (which you should atleast for the Normal map, Ambient Occlusion (AO), and most of the emission (ilm but its only called that in source) and some others if u want to keep parts of the guns normal look) it’s good to put each one on a separate fill layer and then playing these into a folder so you are able to manipulate individual parts.

Now ill cover what which texture map does.

### Diffuse or Base Colour:

It simply defines the RGB value of a given part of the gun and nothing else.

![](<../.gitbook/assets/grafik (10) (1) (1).png>)

### Glossines(sometimes roughness is used instead however the two are not the same):

Defines how shiny or matt parts of the guns are, make sure to not have perfectly flat values for your material as nothing is ever perfectly even, even if u want to make a really smooth surface make sure to have extremely subtle imperfections, this is just how realism works and since none of you will make their own models a realistic style just fits best. Brighter = shinyer.

![](<../.gitbook/assets/grafik (19) (1) (1).png>)

### Emission or Illumination (this time they are interchangeable):

Makes parts of the gun glow, the brighter the value the brighter the glow, it doesn’t replace any colour underneath, be careful as Titanfall has bloom and it can get out of hand fast. Without bloom emission looks a bit worse.

![](<../.gitbook/assets/grafik (5) (1) (1).png>)

### Ambient occlusion:

Just places that are supposed to be darker cuz less light could bounce back to the camera, so basically baked shadows. This is one of the first but not last examples where you can see that substances generators, its baked mesh maps and for example the textures from Titanfall differ by a lot at times.

![](<../.gitbook/assets/grafik (12) (1) (1).png>)

### The normal map:

This is a complicated one. The one you get out of the game is green, we cant use it in this state, you gotta go into photoshop or something similar to flip its blue channel. Its currently only red and green channel to reduce filesize, the blue channel can thus be calculated at runtime as it is dependant on the red and green channels so once you are done with your texturing you should make the blue channel all black again. In blender there is a shader that correctly calculates the blue channel and there’s probably tools online, the imperfections by just making it all white in photoshop aren’t too noticeable though so I did not bother finding out.

The normal maps purpose is to make light reflect differently of a surface then it would with the actual angle to the Lightsource of that surface. So to save performance and aovid capturing every little detail with geometry you can instead have a flat face and create the illusion of a screw trough the normal map.

![](<../.gitbook/assets/grafik (3) (1).png>)

![](<../.gitbook/assets/grafik (9) (1).png>)

### Speceular:

It basically defines how metallic a part of the model looks, if u don’t want something to look metallic at all leave it at its base value, want a purple metal, change the diffuse for all parts where it should have that property to black and then set your spec to that purple. Specular is actually RGB even if it might not look like it in this example.

![](<../.gitbook/assets/grafik (7) (1) (1).png>)

### Cavity:

This map has basically the same effect as AO but its constricted to the tightest of crevasses, I have yet to see anything other then Titanfall use this. Substance doesn’t even include it in its channels so the only use u might get from it is to import it and use it as some mask for a certain effect or something like that. Just use the base games in the skin tool.

![](<../.gitbook/assets/grafik (21) (1) (1) (1).png>)

Height:

This is not a map you get from the game however it is essential to correctly add normal information. Its also black and white and if you want a part of the gun to protrude more outwards it should be brighter then 0.5 luminance or if u want something to dent in it should be darker then 0.5 luminance. 0.5 is the base value and luminance is a pixels brightness.

