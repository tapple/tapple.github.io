---
id: 88
title: Color Buttons
date: 2017-08-16T14:52:59+00:00
author: Tapple Gao
layout: page
guid: http://tavatar.org/?page_id=88
---
<div id="toc_container" class="no_bullets">
  <p class="toc_title">
    Contents
  </p>
  
  <ul class="toc_list">
    <li>
      <a href="#Assembling_a_HUD"><span class="toc_number toc_depth_1">1</span> Assembling a HUD</a>
    </li>
    <li>
      <a href="#Anatomy_of_the_HUD"><span class="toc_number toc_depth_1">2</span> Anatomy of the HUD</a>
    </li>
    <li>
      <a href="#Button_Styles"><span class="toc_number toc_depth_1">3</span> Button Styles</a>
    </li>
    <li>
      <a href="#Additional_HUD_Configuration"><span class="toc_number toc_depth_1">4</span> Additional HUD Configuration</a>
    </li>
  </ul>
</div>

### <span id="Assembling_a_HUD">Assembling a HUD</span>

Step by step instructions on assembling a hud:

  1. Rez the &#8220;Recoloring HUD Template&#8221; on the ground. DO NOT ROTATE IT
  2. Rez a new cube on the ground, behind the template. DO NOT ROTATE IT. This will be the background and the root prim of the HUD, and should show your name as creator.
  3. Add two scripts to the HUD root prim: &#8220;Tavatar Color HUD&#8221; and &#8220;color picker&#8221;. The color picker script may throw an error: &#8220;Color Picker prim is missing from the linkset&#8221;. You can ignore this error, since we will be linking the HUD shortly.
  4. Decide which of the buttons in the template work best for you. Delete the rest. See the section &#8220;Button Styles&#8221; below for more information about the button styles.
  5. For basic buttons ONLY: you may rez your own button prims, as long as they are full perm. Just rename them to &#8220;basic button&#8221;
  6. Duplicate the buttons, if necessary and arrange the HUD how you like. Create textures for the buttons and the background, as necessary.
  7. Change the description of each button to the name of the face group it should control
  8. Link everything together. The background MUST be the root prim.
  9. Try out the buttons and the color picker. Everything should work.
 10. Give the new HUD a good name, and take it to inventory.
 11. Attach the new HUD to one of the HUD attach points. If you avoided rotating the template, background, and set the root prim correctly, it will attach with the correct side facing forward.
 12. If the HUD is facing the wrong way, rotate it until it is showing correctly.
 13. Detatch the HUD

### <span id="Anatomy_of_the_HUD">Anatomy of the HUD</span>

A color HUD consists of several parts:

  * A script named &#8220;Tavatar Color HUD&#8221; in the root prim
  * A script named &#8220;color picker&#8221; in the root prim
  * A color gradient prim
  * A set of color preset buttons (optional)
  * A help button (optional)
  * A set of face group selector buttons

The HUD can be colored, textured, or arranged any way you like as long as it contains these parts. A color HUD works as follows:

  * Click a face group button to select which part of the objects to color
  * Choose a color using either the gradient selector or the preset buttons.
  
    This color will be applied to your objects, and to the HUD button
  * Optionally, save your favorite colors in the preset buttons

The only HUD componets you need to configure are the face group selector buttons. To do that:

  1. Rez or duplicate as many buttons (any style) as you have face groups
  2. Set the prim description of each button to the name of it&#8217;s face group
  3. Link the buttons to the HUD

This is all the script requires. However, the buttons need some kind of label for people to know what they do. The kit provides 3 styles of buttons:

  * text buttons
  * image buttons
  * basic buttons

### <span id="Button_Styles">Button Styles</span>

Text buttons are the easiest to use, but the least flexible. They automatically change their label to the face group name, and resize the button to fit that label. The text of the button will also change color so that it is always readable, no matter what color the button is. The texture and shape of these buttons cannot be changed. Additionally, this button is mesh, so you should avoid it if you have customers that don&#8217;t use mesh. (no other component of the hud is mesh)

Image buttons are similar to text buttons, in that they have two colors: the selected color for the button, and a contrasting color for the label. They are made of a hollow box prim, and so can be used on non-mesh viewers. The foreground and background can be textured independently. This kit provides a set of ready-to-use image buttons providing rounded corners in various sizes. These can be found in the &#8220;Image Button Shape Textures&#8221; box. Also provided are some sample labels used in the sample huds (in the &#8220;Sample Image Button Labels&#8221; box, but you will most likely need to create your own label textures for your own hud. All these textures are also available in the zip file referenced at the top of this document.

Basic buttons are the simplest button type. The entire button prim is colored to match the selected color; no contrast is guaranteed. They can, therefore, be any prim type, including cylinders, sculpties, or mesh. They are therefore probably the best choice if you want to make something other than a hud out of this kit, such as a holo vendor. They are also good for drawing pictures with the button prims, as demonstrated in the &#8220;Sample HUD (Graphic)&#8221;. The kit provides many sample button textures in the &#8220;Sample Basic Button Textures&#8221; box and in the zip file

Here is a side by side comparison of the features of the three button styles:

|                        | Basic | Image | Text |
| ---------------------- | ----- | ----- | ---- |
| Needs custom textures? | Yes   | Yes   |      |
| Requires mesh viewer?  |       |       | Yes  |
| Guarantees contrast?   |       | Yes   | Yes  |
| Flexible prim shape?   | Yes   |       |      |

### <span id="Additional_HUD_Configuration">Additional HUD Configuration</span>

The &#8220;Tavatar Color HUD&#8221; script contains two configurable options. You can change them by editing the first two lines of the script:

<pre>SHOULD_SYNC_ON_ATTACHMENT_REZ
SHOULD_SYNC_ON_HUD_REZ</pre>

By default, when you rez an object while its HUD is attached, it will recolor itself to the HUD colors. You can turn off this behavior by setting SHOULD\_SYNC\_ON\_ATTACHMENT\_REZ to FALSE in the script.

Similarly, by default, when you rez the HUD, it will recolor all its rezzed objects to the HUD colors. You can turn off this behavior by setting SHOULD\_SYNC\_ON\_HUD\_REZ to FALSE in the script.