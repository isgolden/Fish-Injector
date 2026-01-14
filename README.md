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

### Building your level

  first of all, load up your prefered 3D modeling software, i use blender but anything that can import/export obj files will suffice. as of right now, all levels that are loaded are replacements of the basekit island level, or rather, supplementary to it, as it is good practice to leave the basekit island model in place and simply make your level at an offset. so start out by importing the basekit island model that is included with the level editor. once the level is loaded up, you might notice that something doesnt look quite right. that is because the level is sideways. do not worry, they just do that. really though, it is supposed to be like that. the game uses a different upwards and forward direction. that being, forward -z and upwards y. to fix this, you can either rotate the level by 270 around the x axis, or set the default up and forward directions in blenders settings. i recommend doing the latter, as remembering to rotate the level back to the correct orientation is often a large problem when you're loading up a sideways level 5 or so steps up the line.

included in the files is also the texturebox-atlas png, the textures used in the actual game. use this image to set up a material for your level. since it is an atlas, it does **not** tile. this will make texturing a lot more tedious as larger sections will need to be subdivided into smaller rectangles to texture properly.

unfortunately i cant give too much advice on level modeling, i am not very good at it and would rather just adapt someone elses level. (thanks jaspev, even though i really didnt even ask your permission, sorry about that.)

one your level is modeled, remember to rotate it back to the proper orientation, then export it to an obj.

### Setting Up Your Level

if you didn't realise already you need unity installed to continue, specifically version 2023.2. dont worry about knowing how to use unity, you'll only really be using this as an editor, though you could make some changes to my code and add some of your own features, i can't (and won't) stop you.

once you have unity loaded up, open up the included project. Import your level obj under Assets/Import new Asset and drag it into the CustomLevel object, if you did it right, the level should be the correct orientation. if you dragged it into the editor, but not as a child of the CustomLevel object, then it should be rotated, if you drag it into the customLevel object from here, it will keep its orientation, and you will need to reset it manually. this will be a common problem so maybe get used to the process.

Now comes the long checklist of little buttons that need to be pressed or otherwise your computer will explode (if ypur computer is a bomb please take precautions). there is no specific order to these.
  1. mark model and children as static
  2. Go to the "tools" option on the top bar and select Probuilder/probuilder window
  3. select the level and select the option "probuilderize" and click yes for its children. depending on the size of your level, this will hitch for a while.
  4. select the level mesh, in the inspector, tick lightmap static if it isn't already, then press apply.
  5. in the probuilder menu, select "Material Editor" and select default, or Alt-1
at this point, the level is ready to edit. you can use probuidler to further prototype the level without going all the way back to blender.

 ### Placing Dynamic Objects

right click levelObjects in the editor and click "set as default parent", this will allow you to place objects into the scene directly without having to first drag it into the inspector window. in fact, you really shouldn't place any placable's directly into the inspector, it will mess up its rotation unless fixed manually.

 navigate to the asset/placeable folder to get the objects that you can place, each one cana have editable properties in the insspector that you can change, if they do not then only the position and rotation will be saved.

 once you are content with your level, there are a few final things that need to be done.
   1. rename the level object **(not the mesh)** to whatever name you want for your level
   2. drag the mesh **(not the level object)** into the asset window.
   3. select the new level prefab and click on the AssetBundle drop down menu at the bottom of the inspector. click new, then name the asset bundle the name of your level.
you are now ready to export your level!

### Exporting Level

navigate to the top bar and click ScuffedMapBuilder, select "build the bundles", then click "build level information". 

save and close the unity editor and go to the project folder, your level information will be under the Assets folder. what you need to look for is the name of you level with no file extentioin and the name of your level with the .txt extention. follow the installation guide above to import your level into the game.
      




  

