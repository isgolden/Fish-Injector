# Fish-Injector
Custom level loader for The Big Catch: Tacklebox 

this is my first bepin-ex mod and one of my first times using c#, so don't judge the code too hard. or judge it very harshly, i can't stop you.

currently this repo and README acts as a placeholder.

## Installation
-- INCLUDE SECTION ABOUT DOWNPATCHING --

This mod uses the Bepin-ex Unity modding framework, you can download it here: 
https://github.com/BepInEx/BepInEx/releases/latest

once Bepin-ex is installed, move TBCTBLevLoader.dll to Bepin-ex's plugin folder. From there, run the game to generate the config file, found in Bepinex/config.

## Usage
### Loading a Map
if you already have a custom map, move all of its files to the game's streaming data file, (The Big Catch Tacklebox/The Big Catch TackleboxData/Streaming Data). The level should load with the rest of the game the next time you start the game. 

While i am decently sure there will be no problems, i do recommend to either back up your save file or start a new file. if this does happen to you, please report the issue to me.

### Troubleshooting The Loader

The level loader is quite volitile, and can often break through no fault of your own (its probably my fault, but you can balme your computer for both of our sakes'). while there isn't much you can do here, there are some basic options to fix a broken map. first, check the log file in the bepin installation, it should give you an error and _hopefully_ a line/component number. if it didn't give you an error, that means its probably a problem with the map level itself, or the plugin broke.

once you have the line number, find the .txt file for the map (in the streaming data file, if you didn't remember), and delete that line. repeat this until the entire file is gone or the map works. this may result in some objects never loading, but at the very least you can play the map.

## Creating Your Own Map

I have attempted to make the map loading process as easy as i can. WIPWIPWIPWIPWIP

