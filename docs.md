# TarpOS Docs
Official documentation for TarpOS system use and manipulation.

## TarpOSBASIC Commands
Commands are entered as `COMMANDHERE ARGUMENT1 ARGUMENT2 ARGUMENT3`
- <b>savefile</b> - Write file to specified directory - `savefile FILENAME DIRECTORY FILETYPE DATA`
- <b>fetchsystemdata</b> - Returns system data in JSON format - `fetchsystemdata`
- <b>dir</b> - Returns directory contents as an array  - `dir DIRECTORY`
- <b>run</b> - Runs specified program - `run PROGRAM`
- <b>readfile</b> - Returns contents of specified file - `reafile FILENAME ENCODING FLAG` 
- <b>requestrestart</b> - Asks user if they would like reboot - `requestreboot`
- <b>setsettings</b> - Sets system settings and reboots- `setsettings DEFAULTWINDOWHEIGHT DEFAULTWINDOWWIDTH GLOBALFONT`
- <b>github install</b> - Downloads an app from a GitHub repository. The GitHub repository can be for a TarpOS app, but some normal non-TarpOS web apps will also work. - `github install USERNAME REPOSITORYNAME BRANCHNAME`

## Creating a Program
Creating a TarpOS program is easy. Access the TarpOS filesystem on your parent machine by navigating to your computer's documents folder and finding the folder within it called `TarpOS_files`. To get started, create a folder in the `/Programs/` directory. Make sure to name your folder after the program. Next, add/create the following files in your new folder.
- `index.html` - What will display when a user opens your program.
- `app.js` - You can really name this JS file whatever you want, but it's sort of a convention to use `app.js`.
- `icon.png` - This is the icon TarpOS will use when listing your program.  <br><br>
Then, attach `app.js` to your `index.html` file. From there, your program behaves as a normal HTML webpage would. 
To use TarpOSBASIC commands in your app, use `tarpcommands.COMMANDNAME` as an asynchronous function, for example `tarpcommands.readfile("Documents/hey.txt", "utf-8", "r").then((data) => console.log(data));`. The resolve (in our example, `data`) of the asynchronous function contains any return data that the system process sends back.