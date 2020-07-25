# MS3InterviewCode
Parses a .csv file for client records and stores complete records on a database, incomplete records on a separate .csv file, and outputs a log file with totals.

## Summary of the purpose of this repo
This repo is being used for version control and updates for the interview application program for MS3.
The program is designed to ensure that input data is free from corruption before it is saved to a SQLite database file.
Any data that is marked as incomplete is written to a separate output file which can be corrected after the fact and re-run through the program.
The output log file is fairly basic and includes a few statistics about the application's run.

## Steps for getting this app running (for fellow developers)

### Running the program
1.  Download and install the latest version of Java SE JDK (Created using JDK 14.0.2).
2.  Download this repo as a zip and extract it to a folder.
3.  Place the desired .csv file into the newly created folder with the .jar file. The example "Interview" file is provided for ease of use.
4.  Run the .jar file with JDK.
5.  A file selection window will now open.
6.  Navigate to where the .jar and .csv file are saved and open the .csv file.
7.  The window will close and the program will begin running.
8.  Once the application has completed, a window will open informing the user that the parse was successful.
9.  The database file, incomplete data .csv file, and the log file will all be saved in the same folder as the .jar file.

### Opening the project
1.  Download and install the latest version of the Eclipse IDE (Created using 4.16.0)
2.  Download this repo as a zip and extract it to a folder.
3.  Extract the Maven project zip contained within to a separate folder.
4.  Open Eclipse, click file > import > expand the Maven subfolder > Existing Maven Projects > next.
5.  Click browse and navigate to the newly extracted Maven project folder and click open.
6.  

## Overview of your approach, design choices, and assumptions
My approach to designing this application centered around the core philosophy of object-oriented programming.
The creation of the person class is the stepping stone to achieving the goal of writing to the database, but by making this class, I ensure that the data can be tracked in program runtime.
The biggest assumption I made was that this program and the instructions provided are the incomplete version of the client's vision.
Therefore, if the client deems this program as the first version and would like other features or attributes to be stored, the program can be scaled easily to accommodate their needs.
The main shortcoming of this program, at least in terms of being scalable, is the fact that the attributes of the person class are hard coded to the columns of the assigned .csv file.
In learning more through working at MS3, it would be my goal to learn how to programmatically create and assign values to these class attributes.
An important aspect of this program was error trapping, since writing to a few files could have unforseen consequences.
I believe to have done this to the fullest extent, but it is possible that I have missed some type of error.
All current errors are pushed to the user in a window, and the program is then stopped.

