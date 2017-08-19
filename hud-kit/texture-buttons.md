---
id: 51
title: Texture Buttons
date: 2017-08-07T01:41:22+00:00
author: Tapple Gao
layout: page
guid: http://tavatar.org/?page_id=51
---
<div id="toc_container" class="no_bullets">
  <p class="toc_title">
    Contents
  </p>
  
  <ul class="toc_list">
    <li>
      <a href="#1_Load_images_into_the_HUD"><span class="toc_number toc_depth_1">1</span> 1. Load images into the HUD</a>
    </li>
    <li>
      <a href="#2_Create_HUD_Buttons"><span class="toc_number toc_depth_1">2</span> 2. Create HUD Buttons</a>
    </li>
    <li>
      <a href="#3_Associate_a_texture_with_each_button"><span class="toc_number toc_depth_1">3</span> 3. Associate a texture with each button</a>
    </li>
    <li>
      <a href="#4_Remove_the_textures_from_inventory"><span class="toc_number toc_depth_1">4</span> 4. Remove the textures from inventory</a>
    </li>
    <li>
      <a href="#Troubleshooting"><span class="toc_number toc_depth_1">5</span> Troubleshooting</a><ul>
        <li>
          <a href="#Security_Errors"><span class="toc_number toc_depth_2">5.1</span> Security Errors</a>
        </li>
      </ul>
    </li>
    
    <li>
      <a href="#Technical_Notes"><span class="toc_number toc_depth_1">6</span> Technical Notes</a><ul>
        <li>
          <a href="#Texture_Registry"><span class="toc_number toc_depth_2">6.1</span> Texture Registry</a>
        </li>
      </ul>
    </li>
  </ul>
</div>

### <span id="1_Load_images_into_the_HUD">1. Load images into the HUD</span>

Drop all the textures you want to use into the HUD contents

  * Edit the HUD, and go to Contents tab
  * Drag and drop all textures you want to use from inventory to HUD. All textures must be full perm; otherwise, the script won&#8217;t work

The HUD should say something similar to this:

> [07:09] Poncho Hud: AH Texture Master 3.9.7 refreshed inventory; 31 textures loaded. 50.965130% memory available

If any of the textures are not full perm, the HUD will say something like this:

> [07:48] Poncho Hud: Texture &#8220;ExclusiveRFLBunnys&#8221; is not full perm. Ignoring

### <span id="2_Create_HUD_Buttons">2. Create HUD Buttons</span>

  1. Copy some of the texture buttons in the Components object onto your HUD. There are three kinds available: square, round, and text. Use whichever you like.
  2. Replace the prim description with the name of the [face group](http://tavatar.org/hud-kit/clothing-config/) that the button should texture, or the special name CURRENT (all caps, described below).
  3. Once you have a texture button named with each face group, use shift-drag to duplicate as many buttons as you have textures, and arrange them how you want
  4. Lastly, link all texture buttons to your HUD

### <span id="3_Associate_a_texture_with_each_button">3. Associate a texture with each button</span>

  1. Drag and drop a texture that each button should apply onto the front face of the button. The button will now apply this texture to your clothing prims. Repeat for each button, until all buttons are showing the texture they will apply.
  2. Rez or wear your clothing item, and place it behind the hud so that you can watch it during the next step
  3. Close the edit window, and click each button. Each button will say something like this each time you click it:
  
    > [16:59] Template Color/Texture HUD: Texture not found: &#8220;&#8221;; Using button texture &#8220;safetypin-horse&#8221; instead. Prim description updated
    
    This means the button has saved this texture; you will now see the name of the texture in the button&#8217;s prim description if you edit it. If, instead, you see a message like this:
    
    > [17:13] Template Color/Texture HUD: Texture not found: &#8220;&#8221;
    
    This means you forgot to drop that texture into the HUD contents in section 1. Edit the HUD, and drop the missing textures into it&#8217;s contents, then close the edit window and click the button again. (**Note**: You should also see the correct faces of the clothing item being retextured; if the clothing is not updating, check out XXXXXXX Troubleshooting XXXXXXXXX)</li> 
    
      * Make sure you click every button a few times, until none of them are chatting at you. **Important: **If you do not do this step, the texture button will not work after it is sold
      * The buttons now know which textures they will apply. If you like, you may now put a different texture on the buttons. Each button will continue to apply the texture that it saved to it&#8217;s prim description</ol> 
    
    ### <span id="4_Remove_the_textures_from_inventory">4. Remove the textures from inventory</span>
    
    You may have noticed that the hud is chatting this message at you every time you rez it:
    
    > [16:59] Template Color/Texture HUD: chat /74finalize when you are done setting up all texture buttons, and before selling the hud, to protect your textures
    
    Once your hud is complete and about ready to box up, we will do this. First, make sure you have a final copy of the hud, before finalization. Then rez the final copy of the hud, and type
    
    <pre>/74finalize</pre>
    
    The HUD will say something like this:
    
    > [17:22] Template Color/Texture HUD: Cleaning textures from inventory
    
    You may see this error message:
    
    > [17:32] Template Color/Texture HUD: Please remove the no-copy texture &#8220;ExclusiveRFLBunnys&#8221; from my contents
    
    If so, move that texture back into your inventory where it belongs; the HUD is trying to avoid deleting your only copy of a texture if you accidentally dropped in something that&#8217;s no copy. The HUD cannot use textures that aren&#8217;t full perm anyway (as mentioned in section 1 above)
    
    If you edit the HUD, you will now see that all textures are gone. The hud has moved them out of inventory and into it&#8217;s hidden memory contents, where your customers can&#8217;t get to them and use them in ways you don&#8217;t want
    
    If you forget to do this before selling the HUD, the HUD will try to cover for you and silently delete all textures as soon as it&#8217;s rezzed the first time by someone other than you (XXXX CHECK THAT THIS ACTUALLY HAPPENS XXXXX). However, If the customer is clever and rezzes the HUD in a no-script zone, the script will be prevented from running the cleanup code, and your customers will have full access to the texture files. So, it&#8217;s best to always run this before boxing up the HUD
    
    ### <span id="Troubleshooting">Troubleshooting</span>
    
    Are your texture buttons not causing the faces on your clothing item to change texture? Here&#8217;s a troubleshooting checklist
    
    XXXXXX improve the troubleshooting XXXXXXXX
    
    #### <span id="Security_Errors">Security Errors</span>
    
    Pick up and re-rez both the HUD and the clothing item. Do any of them chat **&#8220;Security check failed&#8221;**? If so, fix the other errors mentioned in chat. More details on the security error messages can be found in [the script installation article](http://tavatar.org/hud-kit/texture-script-installation/)
    
    check that the face name in the texture button description matches the face name in the clothing description
    
    > ERROR: No face names have yet been defined for any prim in this linkset. [Here are the instructions for setting them up.](http://tavatar.org/hud-kit/clothing-config/)
    
    check that the passphrases in the texture master script and color slave script match
    
    > ERROR: I recieved an encrypted message, but my passphrase is not set. Please set my passphrase to the same one used in the AH Texture Master script. See [the manual](http://tavatar.org/hud-kit/texture-script-installation/) for more information
    
    check that the channels in the texture master script and color slave scripts match
    
    ### <span id="Technical_Notes">Technical Notes</span>
    
    The format of the text button description is:
    
    <pre>&lt;face name&gt;,&lt;texture name&gt;,&lt;face name&gt;,&lt;texture name&gt;,...</pre>
    
    The script uses the texture&#8217;s name, rather than the more common UUID, because:
    
      1. Name does not need to be kept secret, so is suitable to show in the prim description without worrying about customer&#8217;s abusing it
      2. Name is more readable; you can read the description and know what texture it is, whereas uuid is just a random set of numbers
    
    Every time a texture button is clicked, the following happens (in the function &#8220;fixAndSendConfig&#8221;, in AH Texture Master, line 145:
    
      1. The script reads the prim description
      2. The script checks that all the named textures are in the texture registry
      3. If any are missing, and the texture on the face of the button is known, the unknown textures are replaced with the name of the button texture, and the prim description is updated with the changes
      4. All texture names are replaced with uuid&#8217;s from the texture registry
      5. The special face name &#8220;CURRENT&#8221; is replaced with the face names in the currently active color button
      6. The list of face names and uuid&#8217;s is sent, encrypted, to the Color Slave script in the clothing, where it is applied
    
    So, that means, you can put multiple textures in one texture button, such as a matching upper/lower body texture, although you may need to copy/paste the texture names, rather than using the convenient drag and drop. But for the common case of one texture, one button, drag and drop makes configuration easy
    
    #### <span id="Texture_Registry">Texture Registry</span>
    
    The texture registry is a list of texture names and uuid&#8217;s that the AH Texture Master script knows about. The texture registry can be either editable or finalized
    
    The texture registry starts out editable. In this mode, the texture registry keeps a copy of the full-perm texture names and UUID&#8217;s you add to the HUD&#8217;s inventory. During this time, you can add and remove textures from inventory, and the texture registry will keep a copy. Every time the registry is updated, it says something like this:
    
    > [07:09] Poncho Hud: AH Texture Master 3.9.7 refreshed inventory; 31 textures loaded. 50.965130% memory available
    
    The other state is finalized. This means the texture registry is no longer editable; and there are no longer any textures in inventory. The registry is stored only in the script. When it is finalized, the registry is perfectly safe from snooping; nobody can look at any prims or any script to see the contents of the texture registry
    
    Once the registry is finalized, it cannot be modified, even by the creator. The only option is to purge it and start over, by typing
    
    <pre>/74 reset</pre>
    
    This is why it&#8217;s recommended to only finalize it when you are about to sell your product
    
    The registry can be finalized in one of two ways:
    
      1. The owner, who has modify permissions on the AH Texture Master HUD, types /74finalize
      2. A new owner rezzes the hud while no security errors are active, IE, when it is sold
    
    If you have an alt or business partner and want to transfer the HUD without the inventory being wiped, you should set the hud to transferrable, or set the AH Texture Master script to modifiable (or both), to trigger a security error. Then, you can transfer the hud to your business partner, let them set the permissions properly, and they will have the hud in a texture-editable state
    
    &nbsp;