---
id: 158
title: Tavatar Color / Texture HUD Kit
date: 2017-08-18T05:16:29+00:00
author: Tapple Gao
layout: post
guid: http://tavatar.org/?p=158
permalink: /2017/08/18/tavatar-color-texture-hud-kit/
categories:
  - Uncategorized
---
I updated my Color HUD Kit with texture, alpha, glow, shiny, fullbright, and alpha mode support. I also moved it&#8217;s documentation onto [this website](http://tavatar.org/hud-kit/), since it had gotten too big

<!--more-->

If you are upgrading a color hud from 1.0, please follow these instructions:

  1. Delete all scripts from the hud
  2. Add the script &#8220;AH Colors Sliders Widgets 3.9.2&#8221;
  3. Add the script &#8220;AH Color Buttons 3.9.6&#8221;
  4. If you have any text buttons, add the script &#8220;AH Color Text Button 1.2&#8221;
  5. Unlink the &#8220;Color Picker&#8221; prim from the hud and delete it
  6. Rez the Template hud, and move it&#8217;s Color Picker prim onto your hud, and link it
  7. If you want to add texture changing, delete the Slave script in each object, and insert the script &#8220;AH Color Slave 3.9.6&#8221;. Otherwise, you can leave the slave scripts alone; color, glow, shiny, and full bright work fine with the old slave script