---
layout: docs
title: SpriteSheet
prev_section: color
next_section: none
permalink: /docs/spritesheet/
---

The "SpriteSheet" object allows you to use multiple images at the same time. Sprite sheets 
allow you to compact all of the images and animations in your game into a single image.

## Usage
--------
{% highlight javascript %}
// Load image into Excalibur
var game = new Engine();
var loader = new Loader();
var image = new PreloadedImage("myspritesheet.png");
loader.addResource(image);
game.load(loader);

// Create a spritesheet with the loaded image
var sprites = new Drawing.SpriteSheet(image, 10, 10, 32, 32);


{% endhighlight %}


## Constructor 
<pre>new(public image : PreloadedImage, private columns: number, private rows: number, spWidth: number, spHeight: number)</pre>
--------------

The SpriteSheet constructor takes a preloaded image argument, the number of 
columns of images in your sprite sheet, the number of rows in your sprite
sheet, the width in pixels of each individual sprite, and the height in pixels
of each individual sprite.

## Properties
<pre>spriteSheet.image</pre>
-------------

Gets the internal preloaded image.

<pre>spriteSheet.sprites</pre>
-------------

Gets or sets the list of individul sprites.

## Methods
<pre>spriteSheet.getAnimationByIndices(engine: Engine, indices: number[], speed : number)</pre>
--------------

Returns an "Animation" by specifying the engine, the indices of each sprite in 
the animation, and speed (in milliseconds) that each frame should take in the 
animation. Sprites in the sprite sheet are index in row major order, meaning 
that each sprite is numbered starting at zero beginning at the first row, then 
the second row, etc.

<pre>spriteSheet.getAnimationBetween(engine: Engine, beginIndex : number, endIndex : number, speed : number)</pre>
--------------

Returns an "Animation" by specifying a beginning sprite index (inclusive) and 
an end sprite index (exclusive), and a speed for each frame. Indices are 
specified in row major order.

<pre>getAnimationForAll(engine: Engine, speed : number)</pre>
---------------

Returns an "Animation" treating all of the sprite sheet as members of the 
animation.

<pre>getSprite(index : number)</pre>
--------------

Returns a "Srite" at a specific index in the sprite sheet (in row major order).