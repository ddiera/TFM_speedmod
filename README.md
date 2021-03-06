# TFM_speedmod

NOTE:
-------------
Most features don't work anymore, but if you want to change the game speed just replace "sharedasets0.assets" in your game directory.
Keep in mind this will speed up the end game score tally animation as well!


Instructions:
-------------
To mod your game open the Steam Client and go to "Library" -» right click on Terraforming Mars -» select "Properties" -» click on "Local Files" -»  "Browse Local Files" which will get you to the game directory.
Alternatively you can look up your Steam folder and go to steamapps\common\Terraforming Mars\TerraformingMars_Data.

Make a copy of the following files and save them in a backup folder somewhere:
- TerraformingMars_Data\sharedassets0.assets
- TerraformingMars_Data\resources.assets
- TerraformingMars_Data\Managed\Assembly-CSharp.dll

Download TFM_speedmod.zip and extract the contents then copy the modded files into their respective location as above.\
1, For animation speed changes select the "Ludicrous" option on the Settings panel.\
2, For turning off confirmation popups toggle the "Confirmation Popup" button off in Settings.

note - popups that are disabled by the mod are:\
1, end of turn confirmation\
2, player passed (online game)\
3, player passed (local game)\
4, "no cards selected" warning in research phase\
5, "buy cards after draft" confirmation\
6, first draft phase notification

certain kinds of game-essential notifications still activate - e.g: opponent forfeit, local game player handover, etc

**DISCLAIMER:**\
_By installing you will no longer be able to exploit the Protected Habitat bug, consider this the blood-price to pay if you want to use the mod. ;)
If you are the type of player who enjoys playing dirty you shouldn't be using this mod in the first place._

Known issues:
-------------
- 100x speed modifier is too fast for the productionBar and globalparameterBar animations to handle, remnants of the animation clips remain on screen after they play: http://s000.tinyupload.com/?file_id=56216583134709647930
(cosmetic glitch only, not sure if easily fixable)


Changelog:
----------
v1.07
- mod is now compatible with TFM release v1.1718

v1.06
- fixed game stalling when opponent forfeits ("Opponentforfeit" popup asset does not pause the gameflow anymore)

v1.05
- amended the localization terms of the animation panel tooltip and button label text in "I2.Loc.LanguageSource"

v1.04
- popup activation in "HUD_SimpletextPopup" class is now controlled by "DoDisableConfirmDialogs" toggle settings

v1.03
- modified "HighlightFirstElement" method, online and local games now use the current player as the default target, solo games default to neutral player

v1.02
- "OnTurnSelected" method in "HUD_EndTurnPanel" class is now responsive of "Confirmation Popup" button settings
- "HighlightFirstElement" method in "StealResourceScreen" class no longer pre-selects players on the attack panel 

v1.01:
- "HUD_PassDevicePopup" (Local play) and "HUD_OppenentForfeitedPopup" (Online play) classes now call "DisplayPopup" method in base class on instance
- "Horserace" class is now using hardcoded animation speed float values if mod is active (reverts to scaled settings if mod is inactive)

v1.00:
- changed the animation speed float value in the corresponding "Monobehaviour Slow" assset from 0.8 to 100
- modified "HUD_EndTurnPanel" class in the assembly to deactivate popup activation on instance
- modified "HUD_SimpleTextPopup" class in the assembly to deactivate popup activation on instance
