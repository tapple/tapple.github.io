---
id: 22
title: Tavatar HUD Kit
date: 2017-08-02T16:47:59+00:00
author: Tapple Gao
layout: page
guid: http://tavatar.org/?page_id=22
---
Tavatar HUD Kit is a will help you create a texture changer, color changer, and HUD that you can add to your products in SecondLife. It is available [free on Marketplace](https://marketplace.secondlife.com/p/Tavatar-ColorTexture-HUD-Kit-Free/4299174).

<div id="toc_container" class="no_bullets">
  <p class="toc_title">
    Contents
  </p>
  
  <ul class="toc_list">
    <li>
      <a href="#Introduction"><span class="toc_number toc_depth_1">1</span> Introduction</a>
    </li>
    <li>
      <a href="#Configuring_the_Clothing"><span class="toc_number toc_depth_1">2</span> Configuring the Clothing</a>
    </li>
    <li>
      <a href="#Creating_the_HUD"><span class="toc_number toc_depth_1">3</span> Creating the HUD</a>
    </li>
    <li>
      <a href="#Setting_up_the_Buttons"><span class="toc_number toc_depth_1">4</span> Setting up the Buttons</a>
    </li>
    <li>
      <a href="#Assets"><span class="toc_number toc_depth_1">5</span> Assets</a>
    </li>
  </ul>
</div>

#### <span id="Introduction">Introduction</span>

To get a feel for what the kit can do, 12 sample HUDs are included:

  1. Drop the &#8220;Sample Multi Color Object&#8221; on the ground
  2. Wear any of the 12 sample HUDs. and press all the buttons

There are two parts to setting up a color changing hud:

  * Configuring the face groups
  * Creating the HUD

#### <span id="Configuring_the_Clothing"><a href="http://tavatar.org/colortexture-hud-3-9-instructions/clothing-config/">Configuring the Clothing</a></span>

Every object that the hud will recolor needs to be configured. If you&#8217;d like to have the hud control the color of an object, you need to configure it. There are two ways to configure an object, using either of these scripts:

  1. Edit the object
  2. Open the Contents tab of the edit panel
  3. Drop in the script named &#8220;AH Color Slave&#8221;
  4. Edit the description of the prims in the object

In the simplest case, that the whole object will be the same color and texture. If so, change the description to be &#8220;<face group name>:*&#8221;. For instance, if your face group is named &#8220;fur&#8221;, the description should be:

<pre>fur:*</pre>

The script supports more complex configurations, including separate names for every prim and face in the object. The [full instructions](http://tavatar.org/colortexture-hud-3-9-instructions/clothing-config/) are on a [separate page](http://tavatar.org/colortexture-hud-3-9-instructions/clothing-config/)

#### <span id="Creating_the_HUD">Creating the HUD</span>

Let&#8217;s start by creating a hud

  1. Rez a new cube on the ground. DO NOT ROTATE IT. This will be the background and the root prim of the HUD, and should show your name as creator. Give it a good name, like &#8220;Shoe HUD&#8221;, or something. Leave it as a cube for the moment
  2. Add two scripts to the HUD root prim: &#8220;AH Color Buttons&#8221; and &#8220;AH Text Buttons 3.9.14&#8221;. All HUD&#8217;s require these
  3. If you plan to include a color changer, add the script &#8220;AH Colors Sliders Widgets&#8221;
  4. If you plan to use texture changing, add the script &#8220;AH Texture Master&#8221; and follow it&#8217;s [installation instructions](http://tavatar.org/hud-kit/texture-script-installation/)
  5. While the edit window is open, rez the &#8220;Color/Texture HUD Components&#8221; on the ground. DO NOT ROTATE IT. Move them to be in front of  the cube, and resize the cube to fit
  6. Decide which of the buttons in the component you want to use. Delete the rest. The hud includes 3 types of buttons. The setup instructions on each one are on a seperate page: 
      * [Texture changer buttons](http://tavatar.org/hud-kit/texture-buttons/)
      * [Color changer buttons](http://tavatar.org/hud-kit/color-buttons/)
      * Alpha hide/show buttons XXXX document these XXXX
  7. Link all the buttons to the HUD, making sure the HUD background is the root prim (drag the mouse to select all, shift-click the HUD background twice, then press Ctrl-L to link)
  8. Take the HUD into inventory

#### <span id="Setting_up_the_Buttons">Setting up the Buttons</span>

&nbsp;

&nbsp;

#### <span id="Assets">Assets</span>

In addition to the contents of this box, all textures are available in source form at:

XXXXXXXXXXXXXXXXXXXXXXXXXXX

All were created using open source tools:

  * [Inkscape](http://inkscape.org) vector graphics editor
  * [GIMP](https://www.gimp.org/) raster graphics editor
  * [Blender](https://www.blender.org/) 3D animation editor