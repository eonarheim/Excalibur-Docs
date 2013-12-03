---
layout: docs
title: Label
prev_section: actor
next_section: log
permalink: /docs/label/
---

Labels are a special type of actor meant to be convenient way to display text
on the screen. As a consequence of being an actor, all of the capabilities of
actors come with.

## Usage
--------
{% highlight javascript %}
var game = new Engine();

// Create new lable at x = 50, y = 50, with the text Hello World
var label = new Label("Hello World", 100, 100);

game.addChild(label);

game.start();
{% endhighlight %}


## Constructor 
<pre>new(text? : string, x? : number, y? : number, spriteFont? : Drawing.SpriteFont)</pre>
--------------

The Label constructor takes 4 optional arguments, the text to display, x 
coordinate, y coordinate, and an optional SpriteFont.

## Properties
<pre>lable.text</pre>
------------------

The text to be drawn when the label is drawn. Defaults to empty string.

<pre>label.spriteFont</pre>
------------------

The spriteFont associated with the text if one has been set. Defaults to null.

## Methods

<pre>label.update(engine : Engine, delta : number)</pre>
--------------------

This method is called by the engine to update each label. Delta is the amount
of time elapsed since the last time update was called (in milliseconds).

You should only be calling this method if you wish to extend label.

<pre>label.draw(ctx: CanvasRenderingContext2D, delta: number)</pre>
--------------------

This method is called by the engine to draw each label. Delta is the amount
of time elapsed since the last time draw was called (in milliseconds).

You should only be calling this method if you wish to extend label.


<pre>label.debugDraw(ctx: CanvasRenderingContext2D)</pre>
--------------------

This method is called by the engine when in debug mode. This will add general
debug information to the screen.

## Events

Valid events to listen for off of Label.

<pre>'keydown'</pre>
<pre>'keyup'</pre>
<pre>'keypressed'</pre>
<pre>'update'</pre>
<pre>'click'</pre>
<pre>'mousedown'</pre>
<pre>'mouseup'</pre>

See the events documentation for specifics about each of these events.