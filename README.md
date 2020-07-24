# MS3InterviewCode
Parses a .csv file for client records and stores complete records on a database, incomplete records on a separate .csv file, and outputs a log file with totals.

## Summary of the purpose of this repo


## Steps for getting this app running (for fellow developers)
1.  Download and install the latest version of Java SE (Created using 14.0.2)
2.  Download this repo as a zip and extract it to a folder
3.  Place the desired .csv file into the newly created folder with the .jar file
4.  Run the .jar file with JDK
5.  An input prompt window will now open and ask for the name of the .csv file you wish to parse
6.  Enter the name of the .csv file contained in the folder. IMPORTANT: Exclude the .csv extension!
7.  Click OK or press enter. The window will close and the program will begin running.
8.  An easy way to tell that the program is still running is to look for a .db-journal file in the same folder. This will disappear upon completion.
9.  Once the application has completed, a window will open informing the user that the parse was successful.
10. The database file, incomplete data .csv file, and the log file will all be saved in the same folder as the .jar file.

## Overview of your approach, design choices, and assumptions
