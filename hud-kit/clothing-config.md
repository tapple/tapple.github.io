---
id: 30
title: Clothing Configuration
date: 2017-08-02T16:53:20+00:00
author: Tapple Gao
layout: page
guid: http://tavatar.org/?page_id=30
---
#### Configuring the Face Groups

If you&#8217;d like to have the hud control the color of an object, you need to configure it. There are two ways to configure an object, using either of these scripts:

  * Tavatar Single Color Slave
  * Tavatar Multi Color Slave

The Single Color script is faster to set up, but the Multi Color script is much more flexible. Which script should you use? Answer the following questions:

Do you want this object to have multiple colors?
  
&#8211; If so, you need the Multi Color script

Do you want some parts of the object to not change color?
  
&#8211; If so, you need the Multi Color script

Will the entire object be one color at all times?
  
&#8211; If so, you can use the Single Color script

Does your item consist of multiple attachments or multiple objects you drop on the ground?
  
&#8211; If so, you need a script in each object or attachment. Decide which script is best for each object. You can mix and match them.

Once you have decided which color slave script to use in each of your objects, drop one script into the object. Do not put more than one color slave script into your object. Do not put a color slave script into every prim of your object. I recommend putting the script into the root prim for easy access, but it will work in any prim.

Now you need to configure the face groups that the color slave script uses. This is done differently for the single color and multi color slave scripts. Follow the instructions in one of the next two sections

##### Configuring the Single Color Slave

Every face in a single color object belongs to the same face group. To name that face group:

  1. Edit the object
  2. Open the Contents tab of the edit panel
  3. Double-click the &#8220;Tavatar Single Color Slave&#8221; script
  4. Edit line 2 of the script

By default, this line says:

<pre>string COLOR_GROUP = "alpha";</pre>

Change &#8220;alpha&#8221; to the name of your face group. For instance, if your face group is named &#8220;fur&#8221;, the line should say:

<pre>string COLOR_GROUP = "fur";</pre>

You are done. Press the Save button at the bottom of the script editor, and close the script editor.

To see this in action, rez and examine the included &#8220;Sample Single Color Object&#8221;

##### Configuring the Multi Color Slave

In a multi color object, every face can potentially belong to a different face group, or more than one face group. To configure them, you describe the face layout in the description of each prim. List the face groups the prim belongs to, seperated by commas. If only certain faces of the prim belong to the face group, list the face number after the face group name, seperated by a colen. Examples:

Description: &#8220;fur&#8221;
  
Meaning: This entire prim belongs to the &#8220;fur&#8221; face group

Description: &#8220;body:0,head:1,leftLeg:2,rightLeg:3&#8221;
  
Meaning: This prim is a full body mesh avatar with 4 sections that can be textured and colored independently. Face 0 is the body; face 1 is the head; faces 2 and 3 are the legs.

Description: &#8220;&#8221;
  
Meaning: This prim does not belong to any face groups, and will never change color in response to a command from the hud

Description: &#8220;fur,fur1:0,fur2:1&#8221;
  
Meaning: This prim can be changed in two different ways. The hud can color the whole prim at once by coloring the &#8220;fur&#8221; group. Or it can change faces 0 and 1 seperately, by coloring groups fur1 and fur2, respectively

Tips:

  * To find out which face number belongs to which part of the prim,
  
    add the &#8220;Face Number Helper&#8221; script to the contents of the prim.
  
    Delete it once you are finished.
  * When edit linked parts is enabled, press ctrl-period or ctrl-comma
  
    to quickly cycle through every prim in the object
  * If you change the description of the root prim of an attachment, it
  
    will not stick after you detach it or relog. Either drop the object
  
    on the ground before editing, or edit it directly from inventory by
  
    right-clicking it, and choosing Properties

Sample step by step instructions (You&#8217;ll need to adapt these for your objects):

  1. Edit the object
  2. Enable the &#8220;Edit linked parts&#8221; check box in the edit panel
  3. Open the General tab
  4. Change the description to &#8220;bodyFur&#8221;
  5. Press ctrl-period to select the next prim
  6. Change the description to &#8220;bellyFur&#8221;
  7. Press ctrl-period to select the next prim
  8. Change the description to &#8220;bodyFur:0,bellyFur:1&#8221;

To see this script in action, rez and examine the included &#8220;Sample Multi Color Object&#8221;