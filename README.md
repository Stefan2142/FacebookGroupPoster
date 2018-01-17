# About Facebook Group Poster
Script written for a client to automate posting process to a set of groups provided in a .xlsx file. Important feature is that it can continue from where it left of the previous time. It is built around the ideaa for processing of large number of links. To ensure that your pofile doesnt get blocked, marked as spam/bot and other..a delays were built in. So, at the end of processing each script a random delay ranging between 50-1200 seconds (~1min to 20mins) will be activated. 
Output file is the same as the input but cloned, and renamed to <input_file>+'modified.xlsx'. So you will always have the original intact. 

# Process
Overall pattern of the input file is provided in this repository and should be followed. Otherwise, script wont work. Urls are stored in the first column of the SourceLink sheet and the post content is defined in Data sheet by columns (path to folder with (only) images, album name, description, location (this parameter is not used), HighQuality (should always be set to yes) and the text (caption) for each image (it is the same for all images).  

When the url is processed, in the SourceLink sheet, columns B and C will be populated, first with current date and time and second one with either success or failure. D column will the text of the error (reason why it didnt work).  

At any moment, the script can be terminated and upon next start, it will continue from the last time. That is achieved by writing an index of the row which contains the last url it processed to a report.txt file.

# Requirements
To run this script, two external libraries are needed:  
  * [openpyxl](https://pypi.python.org/pypi/openpyxl)  
  * [selenium](https://pypi.python.org/pypi/selenium)  
  * [chrome web driver](https://sites.google.com/a/chromium.org/chromedriver/downloads)  
  
  
Successful running of the script depends on changing a few lines. So, first a username and password should be added to script (lines 37 and 38). Path to a chromedriver.exe must be updated also (line 72) and a path to the input .xlsx file should be changed in the line 51. 
