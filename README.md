# The-Amped-Gems-Auto-Helper-GUI
The Amped Gems Auto Helper GUI

here is my discord for more info till i relase it 
https://discord.gg/mMA8UKnUNV

https://imgur.com/a/4vq5Mmz

==--====--====--====--====--====--====--====--====--==

Version 1.4
added: inject empty menu 
check 4-inject empty menu  where it does the following:
 * Builds an empty Menu For the First Time and injecting it to the game 
     -- uses template of LGL 3.2 | C:\_AmpedGems\AmpedGemsGUI\template
	 -- uses the second method in implementation not first 
	 PS i can add the first one, it would be better in direct methods, and less messing around with android manifest 
 * it copies original main.cpp into the template folder 
 * it edits the main activity java with the .bitch file created earlier 
 * it assembles a debug menu 
 * moves app-debug to the workspace directory 
 * decompiles app debug 
 * copies lib folder [any lib name allowed]
 * copies smali folder [auto count the smali files and add a new one with the lgl smali]
 * Edits android manifest xml file to handle the menu 
 * once all is done, recompiles apk of the game 

==--====--====--====--====--====--====--====--====--==


Version 1.3
added: 
check 3-  where it does the following:
> it process the game files by doing this:
 * generate codes from the cpp file into methods.c file where it converts any method / field into a menu c++ code where it:
    -- Patch any offset / method 
	-- hook any method [int, bool, long, void, double, float...]
	-- call any method using update 
	-- update / change void methods without using update 
	-- hook any field 
 * opens the methods.c file upon compeletion - make sure to make default opening app for .c files is notepad++ . it will be better.
 * the code is really good, also it will be better, i will be working on that once some major thing in the tools are done. 


Edit to 1- proces game 
> added :
 * added a template to the cpp file 
Edit to 2- dump game 
> added :
  * opening the cpp file after everything is done  -to manually add your methods from dnspy-



==--====--====--====--====--====--====--====--====--==

Version 1.2
added: 
check 2- dump the game into Dnspy where it does the following:
> it process the game files by doing this:
 * closes any open il2cpp dumper 
 * open the il2cpp dumper 
 * get il2cpp, and meta data to dump 
 * dump the game 
 * remove non-needed files 
 * close any dnspy open 
 * open dnspy
 * close the open files inside dnspy 
 * open the new dll files 

edit to 1- proces game 
> added :
 * closes any apktool gui version that is open | since its job is done in the end.

==--====--====--====--====--====--====--====--====--==

Version 1.1
added: 
check 1- proces game where it does the following:
> it process the game file by doing this:
 * closes any apktool gui version that is open 
 * open new clean apktool gui 
 * get apk pacakge name 
 * get apk main launch activity name 
 * get apk Version 
 * if the file is anything other than apk , it will merge it 
 * decompiles apk 
 * you can choose to Prefer 64 or 32  | if the game has 32 bit only and you prefer 64 it is ok , it will not result into error.

Removed: 
 * extension file creator | found a better way for it 
 

==--====--====--====--====--====--====--====--====--==


Version 1.0

Added:
- A cool Title Text with animation at the top of the App
- a button to select a game file:
  * the button opens a window to browse and select a file of the game
    -- currently supports : apk , apks , xapk , apkm, zip 
  * this is the workspace C:\_AmpedGems\AmpedGemsGUI\workspace
  * the workspace will be destroyed and created a new one  
  * the game file will be copied into the workspace
  * the game will be renamed into a.extension 
  * a file with extension will be created 
  * a file with original name will be created  
  * the name of the game will be displayed in the app 
  * the game extension will be displayed in the app 
  
  
  
