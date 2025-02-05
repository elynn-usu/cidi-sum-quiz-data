# Summarized Quiz Data Project
### cidi-sum-quiz-data
Center for Instructional Design and Innovation - Utah State University

* Created by Emma Lynn (e.lynn@usu.edu)
* Supervised by Neal Legler, CIDI Director (neal.legler@usu.edu)
* On request from Jackson Graham, Mechanical and Aerospace Engineering Dept.

This repository contains the code necessary to generate a report showing an overall summary of student data from Canvas quiz attempts.

## Start here!
In these instructions, I will walk you through the entire process of running this program to generate your course data.
We will be running the program using the Command Line. When I give you a command to run, it will look like this:
```
COMMAND
```
Press enter on your keyboard to run the commands once they have been entered.

Commands may or may not output text. Do not worry if some commands do not display anything.

* _A note: the terminal is an entirely text based application, so you won't be able to navigate the text with your mouse, you will need to use the arrows on the keyboard._


### Instructions

First you will need to get a copy of this project onto your computer.

_If you have experience with git and GitHub, feel free to simply clone the project onto your computer in the normal way. Then skip to setting up your environment._

_If you do not have experience with git/GitHub and would like to try cloning the project instead of downloading the project, follow the instructions in the Cloning a Repository section closer to the bottom of this page. 
The benefit of this method is that as maintenance is performed on the program, you will be able to easily access the updated version of the project._

* Navigate to the Launchpad and open the Terminal application on your computer.

* On GitHub, click the green Code button. In the dropdown, click Download ZIP.
* Unwrap the ZIP file.
* Navigate to the downloaded project with the following command.
```
cd Downloads/cidi-sum-quiz-data-main
```

Now we need to set up your environment with your specific settings.
  *  Run the following command:
```commandline
nano .env
```

  *  Your command line has now been turned into a simple text editor. Copy the text below and paste into the file, replacing the filler text with your information.
  ```commandline
CANVAS_API_TOKEN=token
COURSE_ID=course-id
STUDENTS_IN_COURSE=[an upper limit of students]
NUM_QUIZZES_IN_COURSE=[an upper limit of quizzes]
```

* token should be replaced with your personal API key. If you don't have one, see the bottom of this page.
* course-id should be replaced with the id number for your course. It can be found by navigating to the home page of your course on canvas and copying the last part of the url:
  * For example, if your course URL is https://usu.instructure.com/courses/123456, 123456 is the course ID
* [an upper limit of students] should be replaced with a number greater than the number of students in your course.
* [an upper limit of quizzes] should be replaced with a number greater than the number of quizzes in your course.

* Once you have correctly filled in the text, press _CTRL + X_ on your keyboard, followed by the _y_ key, and then the enter key.


* Now, run the following command:
```commandline
pip3 install python-dotenv --user
```

* _If you receive an error here that says something like:_
```commandline
xrun: error: invalid active developer path (/Library/Developer/CommandLineTools), missing xcrun at: /Library/Developer/CommandLineTools/usr/bin/xcrun
```
* _Run:_
```commandline
xcode-select --install
```
* _And try the previous command again._


* Your environment has now been set up!

Running the program:

* Run the following command:
```commandline
python3 generateReport.py
```
* The program will now begin running. Depending on the amount of students and quizzes in your course, it may take a while because of all the necessary API calls.
* When the program is complete, the generated file should be opened in your default .csv application

If you would like to run the program again for a different course, repeat the above steps, beginning at the command:
```commandline
nano .env
```
* IMPORTANT NOTE! You must move or rename the `quizData.csv` file generated by the last run of the program before running it again, or it will be overwritten and your data will be lost.

### Cloning a GitHub repository:
* Run the following commands:
```commandline
cd Desktop
```
```commandline
git clone https://github.com/elynn-usu/cidi-sum-quiz-data.git quiz-data-script
```
```commandline
cd quiz-data-script
```
* _If you receive an error that says something like:_
```commandline
xrun: error: invalid active developer path (/Library/Developer/CommandLineTools), missing xcrun at: /Library/Developer/CommandLineTools/usr/bin/xcrun
```
* _Run:_
```commandline
xcode-select --install
```
* _And try the previous command again._

You should now have a copy of the project on your computer. To get the latest changes before running the program in the future, run the following commands 
(after opening a new terminal window):
```commandline
cd Desktop/quiz-data-script
```
```commandline
git pull origin main
```
The project should update with any changes and bug fixes.

_If you are having issues with cloning the project, feel free to go back and try downloading the zip as is instructed in the original instructions. You can also email me (e.lynn@usu.edu) and I can help you set everything up if you would prefer._

You can now return to the original instructions. Begin at the section on setting up your environment.

## Bug Reports
If something behaves unexpectedly, or you run into a problem with the program, please let me know.

Send bug reports to e.lynn@usu.edu with the subject line "Bug Report - Individual Quiz Data".

Please include:
* What you expected to happen
* What actually happened
* As much output from the terminal as possible - copy and pasted, not in a screenshot
* Look in the cidi-individual-quiz-data-master folder. The files canvasData0000000.txt and contextReport0000000.txt may have been created (where 0000000 is a 7 digit number). Please attach these files to your bug report if they have been created. 
* Your course ID (and specific quiz ID, if applicable)
* What OS you're using (Windows, Mac)
* Any other information that you think could be useful

I will get back to you promptly with an update. Thank you.

## Getting an API key
https://learninganalytics.ubc.ca/for-students/canvas-api/ is a really great resource that walks you through creating an API key.
 Log in to canvas at usu.instructure.com instead of the ubc.ca link, and everything else in the Generate your Canvas access token section should be applicable.
 
Canvas will only show you your token once. Be sure to copy it down somewhere secure. 

**DO NOT share your access token with anyone.**

Anyone with your token has the ability to act as you in Canvas. If you believe your token may have been exposed, delete it right away. (Link to deletion instructions below.)
 Your token should be password protected at the very least.

Deletion instructions: https://community.canvaslms.com/t5/Student-Guide/How-do-I-manage-API-access-tokens-as-a-student/ta-p/273
