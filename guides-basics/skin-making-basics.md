---
description: 'By: Alice'
---

# Skin making basics

## Preping for texturing:

### Fixing the model:

Once you have all your files that you want to use from the game extracted, those being the ptpov\_weaponname for the model and all the guns textures, you should open the modelling software of your choice and fix a few things to make working with it later on easier.

![](<../.gitbook/assets/grafik (2) (1) (1).png>)

So with the charge rifle imported (ptpov\_defender\_v\_defender in files) it is already obvious that its rotation is wrong. This is due to certain programs having a different order in its axis and as you can see it is already rotated by -90° so in my case I just need to set this to 0.

![](<../.gitbook/assets/grafik (20) (1).png>)

Your gun will most likely disappear when u rotate it like that as it does not rotate around its centre of mass which will be fixed in a bit although this is optional. You can also see that its Scale is at 100, the reason for that is similar to the one for the rotation. While this does not matter for Substance Painter it is still best practice to work as cleanly as possible.

Depending on what you did in Legion your files might come with a rig/bones or have all detached faces and so on, I wont cover all those cases but with some understanding of the software you use it should be easy, if tedious, to fix these. Makee sure to not actually edit your model itself as these changed will case issues if you don’t want to bring that model into the game as well.

### Fixing UVs:

The next relevant step is a little bit more hidden but looking at the UVs it becomes more obvious. (I had to switch to my Hemloks file as this issue did not occur with the charge rifle.)

![](<../.gitbook/assets/grafik (13) (1).png>)

Here I have selected a face UV shell that is taking up all of the 1:1 UV space, this comes with the models as another issue trough conversion.

![](<../.gitbook/assets/grafik (6) (1) (1).png>)

Focusing on it in 3D view shows that it’s a one unity big quad inside of the gun. Simply delete it as this taking up the entire UV space will cause issues.

Here it would also be optional to move the Magazine of the gun, if it has one, outside of its holder, depending on weather you care to access the bullets and the part of the magazine inside of the case. On some guns the Magazine might clip into the part of the tun that holds it in. Simply move it a bit to fit. If it’s actually larger than the opening, you can thank respawn.

Now Export it and open Substance Painter. Make sure to Export as an .fbx as its pretty lossless compared to .obj. You can think of this like .jpg and .png just more complicated.

### Exporting:

Under File you need to click export textures.

![](<../.gitbook/assets/grafik (3) (1) (1).png>)

Here you can set your output directory to wherever youd like.&#x20;

Set the output template to what you have used in your project, thus being spec glos. You could also add AO to it but i usually dont care enough.

The file type should be a png and leave it at 16 bits.&#x20;

Set the texture size to whatever your gun usually uses. So based on texturesetsize works. Note that you can make Bigger textures than thebasegames but you would just add a bigger workload on your and anyone elses compute for not much of a benefit as the game looks fine with the textures the way they are.&#x20;

Here you can now click on export and use the Maker version of the skintool to add the skin to the game.
