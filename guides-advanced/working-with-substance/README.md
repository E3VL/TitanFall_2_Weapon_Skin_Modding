---
description: 'By: Alice'
---

# Working with Substance

## Actually making a material that looks good:

Here I will go over how you would use the functionalities I have only briefly covered in the basics docs as it was only focused on getting u started with understanding how things work. I will mostly focus on my marble cars marble material as it’s a good example for making complex materials from the ground up. However I will also get other materials for examples on things I couldn’t cover otherwise. I also wont talk about substances UI or anything if u want to get started with that revere to the basics guide.

The final result:

![](<../../.gitbook/assets/grafik (13) (1).png>)

## Marble:

So with everything setup and your idea in mind you either start with an fill layer or one of the materials substance comes with, they can be selected in the shelf. Its also always good to get some reference of the material you are trying to create.

In my case I just chose a dark green for the base and a glossiness around 0.9 to make it really shiny:

![](<../../.gitbook/assets/grafik (17) (1).png>)

I created a new Fill layer with a brighter green and slightly less glossiness and added a mask to this fill layer.

&#x20;

![](<../../.gitbook/assets/grafik (23) (1).png>)

Black or white doesn’t matter as its initial colour will be replaced though if u want to restrict certain materials to certain parts of the gun you should think about using a white or black mask as it makes a big difference on how much you will work on your mask. White is completely transparent for the layer below to shine through and black is completely opaque.

In this mask I added a fill effect.

![](<../../.gitbook/assets/grafik (38) (1).png>)

In the greyscale slot of this fill I placed a marble\_fine which can be found in the grunges section of your shelf. I added a Levels effect on top to invert this masks white values, you can invert it in the grunges settings itself however with levels you have more control.

![](<../../.gitbook/assets/grafik (3).png>)

![](<../../.gitbook/assets/grafik (9).png>)

As you can see I also clamped the values down to make it much sharper.This is what that looks like now.

![](<../../.gitbook/assets/grafik (28) (1).png>)

It should also be noted that it is generally better to set all textures so also this grunge to Tri-planar projection.

![](<../../.gitbook/assets/grafik (8).png>)

Explaining exactly what it does to UV projection would take to long now so if u actually care [https://substance3d.adobe.com/documentation/spdoc/tri-planar-projection-180191954.html](https://substance3d.adobe.com/documentation/spdoc/tri-planar-projection-180191954.html)

The thing you really need to know is that it keeps your texture evenly sized and it can get rid of seams, though you shouldn’t rely on it. The Car has differently sized UVs on its main side.

![](<../../.gitbook/assets/grafik (31).png>)

![](<../../.gitbook/assets/grafik (25) (1).png>)

These 2 are one piece in the model yet they are separated in the UV, one part is closer to the camera, so it being bigger lets respawn have a bigger resolution to the part where you notice it more. Clever but a bitch for us to work with as the marble pattern is now differently sized on the actual model. Tri-Planar Projection could fix this however in this case and some other Titanfall models it is fucked and doesn’t work correctly.  So what did I do as a work around, I made a new folder with everything identical besides that scale of the pattern, I adjusted it to fit the size difference. One big tip here to save time is using anchor points. A quick explanation of them is that they are also able to be added in the effects dropdown and they can be used to reference properties trough your layer stack. If you add an Anchor Point to a layer can only reference it in layers that are above it not below it. To use them in a new layer you have to click on the layers property you want to effect and then switch over to the anchor points tab and select the one you want to reference.

![](<../../.gitbook/assets/grafik (7) (1).png>)

It’s pretty messy but it works and that’s what’s important with bugs like this.

With anchor points you can also reference your normal maps information to add edgewears not only the parts of the model that are actual geometry but also edges that are only in the normal map. This would then be done under the micro details section where you would have to add the anchor and set the layer to normal.

Back to the actual material.

On the inverted marble mask that I have so far I added a warp to break the shape up some more.

![](<../../.gitbook/assets/grafik (42).png>)

![](<../../.gitbook/assets/grafik (46) (1).png>)

The  warps effect can be pretty sensitive but you can get more control by adjusting the intensity divider.

![](<../../.gitbook/assets/grafik (34).png>)

Then I added a blur in the same way as the warp and also adjusted it.

![](<../../.gitbook/assets/grafik (37).png>)

(yes the warp has become obsolete with this but I wanted to use a better example than the one coming soon)

Here I further reduced it with another levels node.

![](<../../.gitbook/assets/grafik (40) (1).png>)

And I blurred it out again to get a smoother transition from the dark green to the bright green.

![](<../../.gitbook/assets/grafik (44).png>)

Another warp creates a nice stepping effect in the transition which fits to rock, but it’s a worse example for what warp actually does.

And onto this I now added a blur slope which is an effect like a normal blur. It’s a great effect for all sorts of things like creating break up or stylizing a texture. In this case it makes the whole thing more fitting for the rock effect I want to go for.

&#x20;

![](<../../.gitbook/assets/grafik (47) (1).png>)

Now I added another fill with a grunge\_scratches and I set it to multiply so it only effects on top of the pervious areas.

&#x20;

![](<../../.gitbook/assets/grafik (16) (1).png>)

![](<../../.gitbook/assets/grafik (39).png>)

I was pretty happy with this result all I did now was add a paint effect to get the really thick green layers to have a bit more variation. I used the brush dirt 2 its probably one of my favourites. And in the end I decided to lower this masks overall opacity to 56%.

![](<../../.gitbook/assets/grafik (4).png>)

The final layer stack.

![](<../../.gitbook/assets/grafik (21) (1).png>)

Under this layer I added another fill that is almost as dark as the bottom most layer, more blue tinted, and glossier. I used a simple grunge\_marble\_shapes in the mask and left it at its base values.

Its important that you pay as much attention to your glossiness as you do to your colours as its also a really important aspect of realistic materials.

![](<../../.gitbook/assets/grafik (32).png>)

Now all the way at the top of these layers I added a fill layer that is nearly black and added another grunge\_marble\_shapes with a different scale and a slightly lower balance.

![](<../../.gitbook/assets/grafik (43) (1).png>)

Then I added a layer with a bit of a brighter green again and a lower glossiness value with a grunge marble shapes in the mask and 0.3 in balance at a scale of around 5.

![](<../../.gitbook/assets/grafik (26) (1).png>)

I was now pretty much happy with the actual stoney texture so I moved on to adding some cracks, firstly I made some that didn’t lift of to much with the grunge marble\_wide at a high scale again with more or less the same green again but a way lower glossiness of .6 and I made it cave in slightly with the height parameter. Over these I added a warp with an intensity around 3 and a source tiling of nearly one.

![](<../../.gitbook/assets/grafik (19) (1).png>)

Now I made some bigger more noticeable cracks that are now almost white with their colour and go in more on the height. The grunge I sue is marble\_veins with a scale around 3 and a balance of 0.23.

![](<../../.gitbook/assets/grafik (6) (1).png>)

Then I added a layer that is a bit whiter with its colour again and used a marble fine in the mask, on this one I added a sharpen as well to get the corner of the cracks to be sharper.

Here a comparison between sharpened and normal.

![](<../../.gitbook/assets/grafik (11).png>)

![](<../../.gitbook/assets/grafik (2) (1).png>)

![](<../../.gitbook/assets/grafik (27) (1).png>)

New cracks on top, even whiter even bigger. Still marble fine just adjusted the scale. I also added a rather intense warp to this and then sharpened it aswell.

![](<../../.gitbook/assets/grafik (45).png>)

Now I copied this top layer and moved it below all pervious marble veins. I changed the colour to be a more saturated and way brighter green. I then used a blur on what I had to get an area around the veins, so it’s a intense blur at 5.6.

![](<../../.gitbook/assets/grafik (49) (1).png>)

I used a level to get it brighter again.

![](<../../.gitbook/assets/grafik (41).png>)

![](<../../.gitbook/assets/grafik (22).png>)

I blurred it out again then applied a warp to get that Stoney stepping effect and applied a blur slope again.

![](<../../.gitbook/assets/grafik (5).png>)

Now again a fill on top that is set to multiply with an grunge\_dirt\_splats in its greyscale. And I sharpened that result again.

![](<../../.gitbook/assets/grafik (2).png>)

Here I went all the way up the layer stack again and added a fill layer in which I removed the colour channel and only left the glossiness. I set it to around .5 and the grunge I used it grunge\_concrete\_cracked.

![](<../../.gitbook/assets/grafik (35) (1).png>)

Another fill with only gloss, this time a value of .8 and an inverted grunge\_marble\_veins for the mask.

![](<../../.gitbook/assets/grafik (30).png>)

This was now basically my finished material and I moved on to other things. Keep in mind that this is just my way of doing things and substance painter has nearly infinite ways of doing things and getting results. And getting to a result like that isn’t as straight forward as it seemed in this explanation, it’s always way more trying around with what grunges fir where and so on. Also height tends to be less noticeable in game then in substance so a bit more then u think looks good in substance is good for it too have a similar look in game.

Things like the gold highlights.

## Gold:

![](<../../.gitbook/assets/grafik (12).png>)

The process this time is similar, instead of diffuse we use the specular channel now.

So I firstly applied the brass pure base material that is already included in substance.

I Googled the correct RGB values for gold which turn out to be this.

![](<../../.gitbook/assets/grafik (24) (1).png>)

![](<../../.gitbook/assets/grafik (10) (1).png>)

I then applied a mat fx called matfinish\_rough. Matfx can give great results for if you want to create different types of surfaces on metals, there is one for galvanized, brushed, grinded, hammered and many more metals. Try around with them. In the matfx I set use custom grunge to true and used ratio\_grunge\_map\_012 for its input and adjusted its balance and contrast a bit.

![](<../../.gitbook/assets/grafik (48) (1).png>)

I then added the steel rough material on top and used a smart mask to get a nice edgewear from it.

![](<../../.gitbook/assets/grafik (33).png>)

The process was the same as before, try around and find smth that fits, I couldn’t even tell you what I used as substance doesn’t tell me and I forgot by now.

I then added a new fill layer, disabled everything besides glossiness and dragged a ratio\_grunge\_map\_004 into it. I then added a levels to this layer and set it to affect glossiness.

![](<../../.gitbook/assets/grafik (18).png>)

Slightly adjusted.

![](<../../.gitbook/assets/grafik (14) (1).png>)

And that’s the final result of it.

## Glow and extra bits:

My skin had gold cracks on the marble as well, I achieved that by duplicating the gold material and adding one of the marble veins grunges to a mask for it.

I added a 3rd material to the final gun, what I used was steel dark aged, a smart material. I was already with most of it. Usually I would advise against just slapping random smart materials onto your models and leaving it at that as they become pretty noticeable and honestly only look ok in a lot of cases. However on this gun it would be hard to notice and dark steel aged is much rarer and less obvious compared to steel painted rough damaged. So all I did is add a paint to break up its extremely smooth edgewear.

And the glow was pretty simple as well. I added a fill layer at the top of all my layers, gave it an even blue colour, enabled emission and gave it roughly the same colour. The mask I used for it has a fill with substances generated AO. I adjusted it with levels to actually have it appear in the right spots.

![](<../../.gitbook/assets/grafik (36).png>)

This is what it looks like, it should be noted that I inverted it as most of an AO map is actually white so the effect would be the opposite of what I’m trying to create. I then fixed some more things with an paint layer and added a blur to create the illusion of the glow affecting the gun around it.

I then added another fill layer, this time with a pretty blue green and an even greener emissive. Same setup in the mask, just reduced it even further with the levels.

![](<../../.gitbook/assets/grafik (15).png>)

I then added another layer that is bluer again, brighter, and is like the first one again just with the blur being way more intense.

