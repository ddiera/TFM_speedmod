# TFM_speedmod

Instructions:
-------------
To mod your game open the Steam Client and go to "Library" -» right click on Terraforming Mars -» select "Properties" -» click on "Local Files" -»  "Browse Local Files" which will get you to the game directory.
Alternatively you can look up your Steam folder and go to steamapps\common\Terraforming Mars\TerraformingMars_Data.

Make a copy of the following files and save them in a backup folder somewhere:
- TerraformingMars_Data\sharedassets0.assets
- TerraformingMars_Data\Managed\Assembly-CSharp.dll

Download TFM_speedmod.zip and extract the contents then copy the modded files into their respective location as above.
1, For animation speed changes copy and change sharedassets0.assets and select the "Slow" option on the settings panel in-game.
2, For turning off confirmation popups copy and change Assembly-CSharp.dll and toggle off "Confirmation Popup" in Settings 

(note: certain kinds of game-essential notifications still activate - e.g: opponent forfeit, local game player turn phase, etc)


Known issues:
-------------
- 100x speed modifier is too fast for the productionBar and globalparameterBar animations to handle, remnants of the animation clips remain on screen after the animationclip plays
screenshot: http://s000.tinyupload.com/?file_id=56216583134709647930
(slight cosmetic glitch only, not sure if easily fixable)


Changelog:
----------
v1.02
- "OnTurnSelected" method in "HUD_EndTurnPanel" class is now responsive of "Confirmation Popup" button settings

v1.01:
- "HUD_PassDevicePopup" (Local play) and "HUD_OppenentForfeitedPopup" (Online play) classes now activate "DisplayPopup" method in base class on instance
- "Horserace" class is now using hardcoded animation speed float values if mod is active (reverts to scaled settings if mod is inactive)

v1:
- changed the animation speed float value in the corresponding "Monobehaviour Slow" assset from 0.8 to 100
- modified "HUD_EndTurnPanel" class in the assembly to deactivate popup activation on instance
- modified "HUD_SimpleTextPopup" class in the assembly to deactivate popup activation on instance
