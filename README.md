# The-Amped-Gems-Auto-Helper-GUI
The Amped Gems Auto Helper GUI

here is my discord for more info till i relase it 
https://discord.gg/mMA8UKnUNV

https://imgur.com/a/4vq5Mmz

==--====--====--====--====--====--====--====--====--==
Released 1.7.5.1, 1.7.5.2 , 1.7.5.3 today at 11-may-2025
==--====--====--====--====--====--====--====--====--==
from now on, this will be just for moreinfo, the changelog will be in the releases section 
==--====--====--====--====--====--====--====--====--==
Changelog - Version 1.7.5 :
Regarding checkbox 5 "Generating C++ Codes from methods names"
Improved Reliability (Name Conflicts): Fixed potential errors where the script could accidentally generate duplicate C++ function or variable names if the input .cpp file had similar entries. The new version automatically ensures all generated names are unique, preventing downstream compilation issues.

More Robust Complex Hook Generation: Enhanced the way the script handles related code blocks, particularly for the "hook field" and "call method with update" sections in the input file. This leads to 1 shared non repeated structure of the same method when used to update both fields and call methods.

Internal Improvements:
rewrote the whole script logic, the old one was 500 lines , the new one is 1000 lines of codes, everything fixed , tested, and improved.
fixed the whole unknown parameter thing
[you can call a method that is like this ]
public void something(int value , SOMETHING value2)
and change the value or value 2 or both , or even keep the value 2 as is hooked from the game itself, like
public void Damage(int value, Weapon weapon , Type type)
you can hook this method with no errors at all now, you can change the value of the damage, you can keep the weapon, [no need to even create an enum for it] it will deal with all weapons from the game's enum itself , and you can if you want to change the type and return it anything you want. all working now fine and tested on multiple games with multiple scenarios


==--====--====--====--====--====--====--====--====--==
Changelog - Version 1.7.4 :
Regarding  checkbox 3 "injecting empty menu"

Improvements:

Enhanced Stability & Error Reporting:
Improved handling of file operations (copying, reading, writing). The script is now less likely to crash unexpectedly due to missing files or permission problems and will provide clearer error messages if these issues occur.
The main workflow now tracks success/failure more reliably at each major stage (build, decompile, modify, recompile). If a step fails, the script will stop and report the error clearly, rather than potentially continuing with incomplete results.
Ensured the script exits with a clear failure status if any critical step encounters an error.
Improved Responsiveness:
Optimized how the script handles waiting periods and file access, preventing potential freezes or unresponsiveness during these operations, especially when interacting with external tools like the APKTool GUI.


==--====--====--====--====--====--====--====--====--==

update 1.7.3
Changelog: for checkbox 2 "dump the game into dnspy"

Enhanced Stability & Reliability:

Improved the logic for waiting for GUI elements (like main windows and specific controls) in both Il2CppDumper and dnSpy, making interactions less prone to timing issues.

Made the "Close All" action in dnSpy more robust; it will now attempt the action but continue smoothly even if the option isn't available (e.g., no files are open).

Strengthened the cleanup routine to more reliably terminate the Il2CppDumper application upon completion or error.

Improved Feedback & Error Handling:

Significantly increased status logging, providing clearer step-by-step feedback on the automation progress.

Implemented more specific error detection and reporting, making it easier to diagnose failures if they occur.

Internal Improvements:

Refined how background operations are handled for potentially smoother performance, especially when running alongside other tasks.

Optimized the method for finding required game files (libil2cpp.so and metadata.dat).

Essentially, while the core steps remain the same, the new version focuses heavily on stability, better feedback, and more reliable error handling based on the challenges encountered during development and testing.

==--====--====--====--====--====--====--====--====--==
Changelog - Version 1.7.2
for the checkbox 1  "process game file"
Improvements & Fixes:


Enhanced Diagnostics & Error Handling:

Replaced simple print statements with a structured logging system for better tracking of progress and errors.

Introduced specific error types for different failure scenarios (e.g., file issues vs. UI interaction issues), making it easier to understand the root cause of problems when they occur.

Error reporting is now more explicit (using exceptions for control flow) instead of functions returning True/False/None, leading to clearer failure points.

Improved GUI Automation Reliability:

Interactions with the graphical user interface (GUI) of the external tool are significantly more robust.

Includes better checks for when UI elements are truly ready (visible, enabled).

Added retries and verification steps for potentially flaky actions like retrieving or setting text values in the UI, increasing success rates.

Logic for waiting on application readiness and task completion (like decompilation) is more robust and uses dedicated polling mechanisms instead of simple loops with fixed sleeps.

Modernized File/Path Management:

Updated the way file and directory paths are managed using a more modern (pathlib) approach, simplifying path operations and improving cross-platform compatibility.

Refined Asynchronous Operations:

Standardized the way blocking operations (like intense UI interactions or certain file operations) are handled within the asynchronous structure, preventing them from blocking the main event loop.

More Robust Process Management:

Improved the logic for finding and terminating existing instances of the external tool, including better error handling during termination attempts.

Safer File Operations:

File renaming now handles cases where the target filename might already exist.

File creation ensures necessary parent directories exist.

Improved Information Extraction:

Made the extraction of details (like package name, version) from the tool's output more resilient, including fallbacks (e.g., checking version code if name isn't found).

Enhanced sanitization of retrieved names to create safer filenames.

New Additions:


Configuration Constants: Introduced clearly defined constants for timeouts (e.g., how long to wait for UI elements), making adjustments easier.

Workflow Structure: Implemented a clearer separation between the main workflow orchestration, GUI interactions, file operations, and helper utilities.

Concurrent Operations: Utilizes concurrent execution (asyncio.gather) for tasks that can run in parallel, such as creating multiple marker files or processing multiple .cpp files, potentially speeding up parts of the process.

Explicit Cleanup: Added a dedicated cleanup step that ensures the external tool's process is terminated even if errors occur during the main workflow.

Asynchronous File Handling: Uses asynchronous file I/O (aiofiles) for potentially large file operations like appending the template, improving responsiveness.

Dedicated Helper Utilities: Introduced reusable helper functions for common tasks like running blocking code safely (run_blocking) and waiting for conditions asynchronously (async_wait_for_condition). 
Removals / Replacements:


print for Diagnostics: Replaced almost all print calls with logging.

Basic try...except Exception: Replaced overly broad exception catching with more specific error handling and custom exception types.

Boolean/None Return for Errors: Replaced the pattern of functions returning True/False/None to indicate success/failure with raising specific exceptions.

Manual time.sleep in Async: Removed blocking time.sleep calls within asynchronous functions; delays are now handled by asyncio.sleep or implicitly within waiting functions.

Direct os Module for Paths: Replaced most direct uses of the os module for path manipulation with pathlib.

Less Structured Async Helpers: Replaced older patterns for running blocking code in threads/executors with the standardized run_blocking helper.

Removed Unused Code/Imports: Eliminated unused global variables and unnecessary imports (threading, shutil, datetime, functools where no longer needed).

In summary, the new version represents a significant refinement focusing on robustness, maintainability, diagnostics, and efficient handling of asynchronous operations and GUI interactions. It addresses potential failure points found in the older version and structures the code more clearly.
==--====--====--====--====--====--====--====--====--==

Changelog - Version 1.7.1
This update focuses on improving the stability, reliability, and feedback mechanisms of the tool.

Improvements:

Centralized Logging: All operational messages, status updates, warnings, and errors are now consistently displayed within the main log window (the text box). Pop-up messages have been removed for a more streamlined experience.

Enhanced Stability: Improved error handling throughout the process. The tool is now more resilient to unexpected issues during script execution and file operations.

More Responsive Cancellation: The 'Stop' button is now more effective at halting operations, including during the later stages like folder cleanup.

Clearer File Status: The labels indicating Package Name, Activity, and Version will now more accurately display "Not Found" or "Error" if the corresponding files cannot be located or accessed properly.

Game File Selection Reliability: Made the process of selecting a game file and preparing the workspace more robust, reducing potential errors during setup and cleanup.

Improved 'Enter' Command: Increased the stability when sending the 'Enter' command to scripts that require manual input confirmation.

Fixes:

Sequential Execution: Fixed an issue where subsequent scripts might run even if a preceding script failed. The execution sequence will now reliably stop immediately upon encountering the first script failure.

File Identification: Improved the reliability of identifying necessary project files within the workspace.

This version aims to provide a smoother and more predictable user experience.
more improvements to come , to the existing things 
then full new things to be added to the tool 

==--====--====--====--====--====--====--====--====--==

Version 1.7
added: 7- Back up the database file of the codes  
check 7-  Back Up Database  where it does the following:
 * the database file of packagename.cpp will be added to the database folder , if the old file existed it overrites 

==--====--====--====--====--====--====--====--====--==

Version 1.6
added: 6- inject full menu
check 6- inject full menu  where it does the following:
 * it will inject full menu into the one that was already injected with empty menu 
   ** builds a menu from the methods.c file 
   ** get the app debug and decompiles it 
   ** inject the app debug files into the game files 
   ** recompiles the game folder 
   ** changes the name of the game to its own name , and version , and adds signed, to know the mod  -later will add unsigned option for you-
   example : Erythros_v24.02.25_signed.apk
   
edited 3,4,5 to be in a better order 
 * 3 now is inject empty menu 
 * 4 update offsets 
 * 5 generate cpp code 
 * edited the fail safe now to be 3 not 4 

==--====--====--====--====--====--====--====--====--==

Version 1.5
added: 
check 5-update current offsets where it does the following:
 * the file methods.c has methods names and signatures in dump.cs file, so it takes these and seaches in the dump.cs and updates the offsets 
 * if something is wrong it will tell you , to fix it manually so when you make auto mod it does not fail 
 * Nested Classes do not get updated | but i have a fail safe in place for it to catch it , so you can manually either remove it or update it manually


added:
a stop button :
 * incase you wanted to stop in the middle of a process , but be careful when you re click run, it will coninue like it was first clicked, all checked processes will start from begining 

edited 4 
 * added a fail-safe for check box 4 , cause it is senstive to the files, i did not want you do a mistake and reboot your whole operation 
 * it gets deleted when you select a new game , so it can be run once per game , even if the whole PC got restarted .
edited select game
 * it shows the file name normally like "game.apk" in the game name area then when you run "1- process game... " , it  gets the real game name 
 * edited Run button , now it disables itself till the script is done running, to prevent acciedental clicks. preventing errors of that type
 
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
  
  
  
