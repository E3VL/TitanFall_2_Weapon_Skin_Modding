---
description: 'By: Alice'
---

# Substance

## Basics of substance explained:

Firstly go to file and make a new Project.

![](<../.gitbook/assets/grafik (11).png>)

In this windows we need to first select the Template, there is many ways of creating the same effects and in the case of Titanfall or Source (im not sure honestly) the one used it Specular Glossiness. Next select you fbx file, set the document resolution to what is used in game, that is 2k for most guns however some like the wingman actually use 1k resolution on their textures, however if u want to you can still make 2k resolution textures for guns like the wingman elite. The problem here would then be that it takes a greater amount of performance even though the base games resolution would have looked fine. Here you can now just click on ok to import your model.

You should save your project now to actually not just have an unnamed project and frequently later on. There is autosave but u shouldn’t rely on it. Depending on your hardwares power substance might crash at seemingly random points so you might loose a good bit of progress.

The next important step is baking your mesh maps. On the right you can see your layers and next to it are your texture set settings.

![](<../.gitbook/assets/grafik (1) (1).png>)

If you don’t see the textures set settings window you need to open them further on the right.

Scrolling down a bit you can see your channels. Click the plus to add ones called emission and ambient occlusion. You should not remove anything if you have used the right Template.

![](<../.gitbook/assets/grafik (17) (1).png>)

Scroll down a bit and click on bake mesh maps.

Uncheck ID, set the output size to 2k and that’s all you rly need to do here for Titanfall skins.

![](<../.gitbook/assets/grafik (18).png>)

Click either bake your guns name or bake selected. Wait for it to compute all your texture maps.



### UI:

![](<../.gitbook/assets/grafik (8).png>)

On the left there is your 3D View, on the left your 2D UV layout, by pressing f2 or f3 you can isolate either one and go back to both with f1. On the right you can see your layers with all respective options and right bellow the properties of your selected item. At the bottom you can see your assets, these are presents of Smartmaterials, materials, textures, masks, brushes, generators and alphas. Importing your own is possible for all of these. And on the left you can see your tools like brushes stamps and so on. In your 3d or 2d view at the top right you can see a dropdown in which you can isolate individual channels of your materials, like colour, normal, glossiness, the ones substance has generated like world position and also things like your current mask.

### Quick Substance introduction:

You usually start of by thinking of a design and then creating a fill layer, changing its attributes to resemble some basic aspect like, for metal you could create something grey in spec and have a bright value in its gloss spot to make it very shiny, these values are set in the properties under your layers. Then you should create a folder that you place that fill layer in, add a mask, masks are more see trough on brighter values and more opaque on darker values. In that mask you add a paint effect under your effects dropdown.

![](<../.gitbook/assets/grafik (14).png>)

In this paint you can now easily edit the mask and define on what parts of the gun you want your folder to be visible, you can edit the mask directly but this is hard to manipulate or change later so id advise against that. The easiest way to restrict your materials to certain parts is to go all the way to the left of substance, and then the 4th tool from top called polygon fill will be useful here. You can select between polygon and triangle fill, as all models extracted from engines are already triangulated these are effectively the same, the UV chunk fill which selects your individual continuous UV shells that you clicked on, visible in the UV view, or your object fill mode you are currently working on an whole Model but it is still made up of individual surfaces which are not connected, and these are what you are selecting here.

In that created folder u can now place a different fill layer on top and add a mask again. Now this is where the real fun begins as I will now explain all the different ways you can add effects on top of each other to create more realistic looking materials.

You could add a fill effect and then go into your assets browser/shelf, to the grunges section, take one that fits and drag it into the grayscale slot, now u can change settings in that grunge to change how it affects the mask and lower the effects opacity in general, if you are familiar with layer modes in photoshop these can be changed in your mask where your fill effect was applied as well.

You could also add a generator to get your mask to only affect places where your AO is stronger or your do the same with curvature of thickness or to get a 3d gradient.

In your shelf you can also see a section for smart masks, these are a collection to of premade masks to help you speed up your workflow for creating certain effects like dust or edgewear.

You could also add a Filter on top of your already existing stack in that effects stack to add for example a blur, or slope blur which is good to chip up textures or stylize them, or adding a sharpen.

You can add levels to have some great control over the luminance of your mask.

And you can add all of these things and many more together to create great textures, or fuck up everything and want to die.
