# MS3InterviewCode
Parses a .csv file for client records and stores complete records on a database, incomplete records on a separate .csv file, and outputs a log file with totals.

## Summary of the purpose of this repo
This repo is being used for version control and updates for the interview application program for MS3.
The program is designed to ensure that input data is free from corruption before it is saved to a SQLite database file.
Any data that is marked as incomplete is written to a separate output file which can be corrected after the fact and re-run through the program.
The output log file is fairly basic and includes a few statistics about the application's runtime.

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
5.  Click browse and navigate to the newly extracted Maven project folder and click select folder.
6.  Click finish and open the project in the project explorer.
7.  Right click the Maven project superfolder and click properties.
8.  Select Java Compiler from the list on the right and select the version noted above.
9.  Right click JRE System Library and select properties.
10. Select the workspace default radio button and click apply and close.
11. The two classes for this project, CSVParse and Person, can be found under the Maven project folder name > src/main/java > maven.SQLite.TestDB.

## Overview of your approach, design choices, and assumptions
My approach to designing this application centered around the core philosophy of object-oriented programming.
The creation of the person class is the stepping stone to achieving the goal of writing to the database, but by making this class, I ensure that the data can be tracked during program runtime.
The biggest assumption I made was that this program and the instructions provided are the incomplete version of the client's vision.
Therefore, if the client deems this program as the first version and would like other features or attributes to be stored, the program can be scaled easily to accommodate their needs.
The main shortcoming of this program, at least in terms of being scalable, is the fact that the attributes of the person class are hard coded to the columns of the assigned .csv file.
In learning more through working at MS3, it would be my goal to learn how to programmatically create and assign values to these class attributes.
An important aspect of this program was error trapping, since writing to a few files could have unforseen consequences.
I believe to have done this to the fullest extent, but it is possible that I have missed some type of error.
Any Relevant errors are pushed to the user in a window, and the program is then stopped.
I tried to keep the core building blocks for the program as simple as possible, while the complexity in the program is derived from the connections between these simple building blocks.
For example, the parse through the input .csv file is a while loop which checks that the next line has some data and if it does, it continues running. It then instantiates the Person class passing the data of the current row through and assigns the values of each row to each attribute. A simple for loop checks for any incomplete columns and sets the corresponding boolean attribute of the person object to true if there is missing data. Finally, an if statement checks this attribute and assigns the person object to one of two arraylists depending on their completeness.
I also tried to keep UI simple and the runtime as light as possible.
Documentation resides within the project as well in order to aid in the reading of my code, and I tried to keep the formatting as consistent as possible, but there is likely some inconsistencies.
Finally, I discovered a couple of things when checking the incomplete output .csv.
Firstly, I had to re write my code to accomodate for the commas located within the image column as they were being read as a delimiter.
Second, this isn't exactly an error, but many of the entries in the final column appeared to be corrupted from the original input file and a fix that I found was changing the encoder to Unicode UTF-8.
Finally, I ultimately chose to set the data type of the H and I columns to boolean, but they display as numbers with values of 0 or 1.
The output incomplete data .csv file retains the original format so that the missing data can be filled in and the file re-run through the program.
