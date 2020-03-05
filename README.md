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
2, For turning off confirmation popups copy and change Assembly-CSharp.dll.


Known issues:
-------------
- 100x speed modifier is too fast for the productionBar and globalparameterBar animations to handle, remnants of the animation clips remain on screen after the animationclip plays
screenshot: http://s000.tinyupload.com/?file_id=56216583134709647930
(slight cosmetic glitch only, not sure if easily fixable)

- endgame scoring animation ("Horserace" class) is too fast due to being affected by the animationspeed modifier, takes away the excitement of the final tally
(FIXABLE: can be forced to use hardcoded float values in the script to enforce normal animation speed)

- opponent forfeits don't show up when the AI takes over
(FIXABLE: "HUD_OpponentForfeitPopup" class is using "HUD_SimpleTextPopup" as base class, need new logic in script to identify forfeit instance)


Changelog v1:
-------------
- changed the float value in the corresponding "Monobehaviour Slow" assset from 0.8 to 100
- modified "HUD_EndTurnPanel" class in the assembly to deactivate popup activation on instance
- modified "HUD_SimpleTextPopup" class in the assembly to deactivate popup activation on instance
