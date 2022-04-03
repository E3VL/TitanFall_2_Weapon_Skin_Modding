---
description: 'By: Alice'
---

# Convert Metal Rough to Spec Gloss

&#x20;Ok so depending on what you do and how much effort you want to put in to your materials in substance you might need to work in metalic roughness and specular glossiness.&#x20;

## Introduction

![](<../../.gitbook/assets/grafik (20).png>)

So this material was created in substances metalic roughness template. What is taht though?

Well it achives the same as spec gloss, just in a different way. In spec gloss a dilectric material, so something that isnt metalic, gets its color from the diffuse and its shinyness from the glossiness. And a metalic material gets its color and metalic look from the specular map while the diffuse needs to be all black, and its shinynes is also taken care of by gloss.&#x20;

And in metalic roughness a materials color is driven by diffuse, metal or not does not matter. So the metalness mal is just a slider between one and 0, white and black, that determins how metalic that part of the diffuse is. There are no matterials that that are something between metal and not though so if you care about realism even in the slightest you should keep it at either white or black.

And a roughness map is simply a glossiness map inverted, so black is shiny and white is rough while for a gloss white is shiny and black is rough. You might ask why they are even different maps when they are so similar, and the answer ist that there is no reason. At least to my knowledge, this has just historically grown to be the way it is i guess.&#x20;

Personally i like metal roughness more because thats whats used in 90% of games and other uses and its also easyer as you just have a diffuse for all color and then a boolean for metal or not.

## How to convert it

So as I have already said converting gloss to rough is trivially easy. You do not have to do anything more then loading the file into photoshop, pressing ctrl + i, and then saving the result.

To get your specular however the process is a little more involved. Because you cannot simply put your diffuse into your spec channel unless no part of your gun is supposed to have diffuse color.

So if you have a metal map and a diffuse you can basically use the metal map as a mask in photoshop to make all your diffuses parts that are specular completely black, and then you can copie paste those parts into your spec map.&#x20;

If you want to covert spec to metalness you need to make the specs parts that are metallic completely white and the rest black. The easiest way to get that would be to colorselect all black parts of your diffuse, and then using that as a mask to copie paste your spec ontop and then making all those parts white and the rest black for your metalness map.

You dont have to use photoshop, just something that can do the described actions.



### More indepth information

[https://www.youtube.com/watch?v=mrNMpqdNchY](https://www.youtube.com/watch?v=mrNMpqdNchY)
