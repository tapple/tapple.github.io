---
id: 42
title: Texture Script Installation
date: 2017-08-06T23:53:27+00:00
author: Tapple Gao
layout: page
guid: http://tavatar.org/?page_id=42
---
How to set up texture change buttons in your hud. I will use in my example a HUD named Poncho Hud. It is part of this product on marketplace: XXXXXXXXXXXXXX

<!--TOC-->

# Installing the Texture Master Script in the HUD

Rez the HUD on the ground and add the script &#8220;AH Texture Master&#8221; to HUD. It will chat some instructions on how to set it up. Taking the instructions one at a time, here&#8217;s what they mean in detail:

> [17:06] Poncho Hud: The script &#8220;AH Texture Master 3.9.7&#8221; needs a passphrase in order to work. Please edit the script and set a passphrase at the top. You will also need to set this same passphrase in the Color Slave script you add to the worn items. Here&#8217;s a random suggestion:
  
> string passphrase = &#8220;AtMjKWuAGbxWziz6 Poncho Hud EIkRsODIFNPrB60L&#8221;;

Passphrase is a piece of text used to encrypt your texture uuid&#8217;s so that they cannot be stolen by a simple LSL script.

  1. Edit the HUD, and go to Contents tab
  2. Double-click the script &#8220;AH Texture Master 3.9.7&#8221; to open it
  3. Copy the suggested random passphrase into line 1 of the script, replacing the empty passphrase that is there, for instance: 
    <pre>string passphrase = "AtMjKWuAGbxWziz6 Poncho Hud EIkRsODIFNPrB60L";</pre>

  4. Save the script

The passphrase also needs to be copied to the slave script; I will describe that process in detail in the next section

> [17:06] Poncho Hud: Script &#8220;AH Texture Master 3.9.7&#8221; must have next owner permissions of no modify

  1. Edit the HUD, and go to Contents tab
  2. Right-click the script &#8220;AH Texture Master 3.9.7&#8221;, and choose &#8220;Properties&#8221;
  3. Uncheck the checkbox labeled &#8220;Modify&#8221;

> [17:06] Poncho Hud: chat /74finalize when you are done setting up all texture buttons, and before selling the hud, to protect your textures

/74finalize is described in more detail in this article: XXXXXXXX

> [17:06] Poncho Hud: Set this prim to no transfer

  1. Edit the HUD, and go to General tab
  2. Uncheck the checkbox labeled &#8220;Transfer&#8221;

> [17:06] Poncho Hud: AH Texture Master 3.9.7: Security check failed. Disabling script. Fix the issues and re-rez to try again

If you followed all the instructions above this line, you have fixed the issues. Right click the HUD and Take it. Then, rez it again from inventory. This time it should not say &#8220;Security check failed&#8221;. If it does, repeat the above instructions. If the script is installed properly, it should say something like this:

> [17:34] Poncho Hud: chat /74finalize when you are done setting up all texture buttons, and before selling the hud, to protect your textures
  
> [17:34] Poncho Hud: AH Texture Master 3.9.7 refreshed inventory; 0 textures loaded. 60.712600% memory available

If so, you are ready to proceed with installing the slave script in the clothing prims, then we can start adding the textures

# Installing the Color Slave Script in the Clothing

Every clothing item to be used with this kit needs to have the script &#8220;AH Color Slave&#8221; inside. The script can be used unmodified if you are only using the hud as a color changer. However, it needs additional setup if it is used for texture changing. To protect your textures from casual theft by a simple LSL script, they are encrypted during transit from hud to clothing. This encryption needs to be set up.

If you have multiple attachments to configure, configure one of them fully. Once the script is set up, you can copy the configured script to every other attachment

Start by dropping the script &#8220;AH Color Slave 3.9.6 (Unlocked)&#8221; into your clothing item. In my examples, my clothing item is named &#8220;Teegle Horse Poncho&#8221;. Now edit it as follows:

  1. Edit the Clothing item, and go to Contents tab
  2. Drop the script &#8220;AH Color Slave 3.9.6 (Unlocked)&#8221; from inventory into the clothing contents
  3. Double-click the script &#8220;AH Color Slave 3.9.6 (Unlocked)&#8221; in the clothing contents to open it
  4. Copy the same passphrase you used in Texture Master script into line 1 of the script, replacing the empty passphrase that is there, for instance: 
    <pre>string passphrase = "AtMjKWuAGbxWziz6 Poncho Hud EIkRsODIFNPrB60L";</pre>

  5. Save the script

The script will now chat additional setup instructions, like so:

> [18:16] Teegle Horse Poncho: The script &#8220;AH Color Slave 3.9.6 (Unlocked)&#8221; needs to save your account key in order to work. Please edit the script and set your key as creator at the top, like this:
  
> key creator = &#8220;a98362e9-bb71-45d0-aebe-3f0184f934fc&#8221;; // Tapple Gao

  1. Edit the Clothing item, and go to Contents tab
  2. Double-click the script &#8220;AH Color Slave 3.9.6 (Unlocked)&#8221; in the clothing contents to open it
  3. Copy your avatar key onto line 4 of the script, exactly as instructed, for instance: 
    <pre>key creator = "a98362e9-bb71-45d0-aebe-3f0184f934fc"; // Tapple Gao</pre>

  4. Save the script

The script will now chat yet more setup instructions. If it does not, you probably mistyped your creator key. Copy and paste it exactly as the script instructed. Don&#8217;t use my creator key.

I will walk thru the remaining setup instructions one by one:

> [18:23] Teegle Horse Poncho: This object must have next owner permissions of no transfer. Please rez me on the ground and change my next owner permissions

  1. Edit the Clothing item, and go to General tab
  2. Uncheck the checkbox labeled &#8220;Transfer&#8221;

> [18:23] Teegle Horse Poncho: Please set the next owner permissions of script &#8220;AH Color Slave 3.9.6 (Unlocked) &#8221; to no modify. This protect the encryption passphrase, which helps protect the textures

  1. Edit the Clothing item, and go to Contents tab
  2. Right-click the script &#8220;AH Color Slave 3.9.6 (Unlocked)&#8221;, and choose &#8220;Properties&#8221;
  3. Uncheck the checkbox labeled &#8220;Modify&#8221;

> [18:23] Teegle Horse Poncho: Security check failed. Shutting down script &#8220;AH Color Slave 3.9.6 (Unlocked)&#8221;. Fix the issues and re-rez or reset the script to try again. For more information on the security checks, or to disable some of them, please open the script and read the top section

If you followed all the instructions above this line, you have fixed the issues. Right click the Clothing item and Take it. Then, rez it again from inventory. This time it should not say &#8220;Security check failed&#8221;. If it does, repeat the above instructions. If the script is installed properly, it should not chat anything.

I advise renaming the slave script to indicate that it&#8217;s no longer unlocked, but is keyed to your hud. I renamed mine to: &#8220;AH Color Slave 3.9.6 (Tapple Poncho)&#8221;:

  1. Edit the Clothing item, and go to Contents tab
  2. Right-click the script &#8220;AH Color Slave 3.9.6 (Unlocked)&#8221;, and choose &#8220;Rename&#8221;
  3. Type in a new name, for instance, &#8220;AH Color Slave 3.9.6 (Tapple Poncho)&#8221;

Now, copy the renamed script from the clothing item back into your inventory. If you have further clothing items to set up, simply drop the renamed script into each one. The script may ask you to set the other attachments to no transfer, but that should be the only setup needed on the rest of the clothing items.

# Next Steps

The scripts are now installed and in your HUD and clothing items. You can proceed to either add the textures to your HUD, and then configure where each one goes on the prims:

  * [Adding Texture Buttons](http://tavatar.org/hud-kit/adding-texture-buttons/)
  * [Clothing Configuration](http://tavatar.org/hud-kit/clothing-config/)