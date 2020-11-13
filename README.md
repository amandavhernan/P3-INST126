# Project 3: Employee Log Report
## Group Members: Amanda Hernández, Alexandra Glick

## Overview

This is our third project for INST126 at the University of Maryland. For this project, we are pretending to be a part of a
professional working environment. Within most work environments, most software and digital activities are recorded using log files and that's where we come in. 
First, it's important to understand that the files analyzed contain information spanning a month. There are also 50 different employees. So, we first assesed the problem statement and came up with a plan of action that detailed how we would work through the problem. 

The goal of this program is to issue four reports that provide insights in four areas: suspicious activity, irresponsible behavior, system glitches, and domian countes. We will also provide an additional report that looks at which employee works the most. Ultimately, these reports are supposed to be used by higher officials to make decisions. 

## How it works

At first, we were expecting our code to consist of a total of five functions and one main dictionary data structure that will return all necessary information for each function; however, things didn't seem to go the way we had planned. After discussing this for a while, we decided to create only 2 functions, "logFile" and "writtenReport." The "logFile" function was created to read the userlog.log and store that data into one big dictionary, named "logsDict," consisting of several rows and columns includuing information about the users. The first column in each row represents the "Date and Time" of the activity. The second column of each row represents the "User Activity", including "login" and "logout." The third column of every row represents the "Server" from which the activity of the user has occurred and the fourth and final column gives the specific Email-ID of the user. To generate each report using the information in the dictionary, we cohesively and in an organized manner generated code to track suspicious activities, irresponsible behavior, system glitch, and domain count. When a user first runs our program, the log file will be read and stored into the dictionary "logsDict." Next, the "writtenReport" function will be generated, giving each report the correct instructions to be printed into each report file. Lastly, the suspicious activities, irresponsible behavior, system glitch, and domain count reports will be implemented respectively. 

### Tracking suspicious activities

To generate our first report, we created a dictionary called "susActivity" and set a variable, named "susCount" to 0 to begin with. Next, we utilized iterations in order to create expressions for the variables "loginCount" and "lateLogin." Next, we implemented two conditional statements; the first conditional statement checks if an employee logged into any of the system servers (mailserver.local, myworkstation.local, or webserver.local) more than five times in one single day. The second conditional statement checks if any employees logged in between 12:00 a.m. and 5:00 a.m. in one single day. Those who logged in more than five times or  in between 12-5 a.m. in one single day will be marked as suspicious. 

The following code represents our conditional statements:

      if loginCount > 5 or lateLogin:
            susCount += 1
            if user_email in susActivity:
                susActivity[user_email].append(date)
            else:
                susActivity[user_email] = [date]
            sorted(susActivity[user_email])

Lastly, the program will return the total number of suspicious activities and append it into a new text file, called "suspicious_report.txt."

### Tracking irresponsible behavior 

To generate our first report, we created a dictionary called "irresBehavior" and set a variable, named "irresCount" to 0 to begin with. Next, we utilized iterations in order to create expressions for the variables "loginCount" and "logoutCount." To implement this code correctly, we created two conditional statements; the first conditional statement counts the number of times each employee has logged into any of the systems and the second conditional statement  counts the number of times each employee has logged off. An if statement stating if the number of logins are greater than the number of log offs will be implemented. If that statement is true, it will be marked as an irresponsible activity and "irresCount" will increase by one.

The following code represents our conditional statements:

if loginCount > logoutCount:
            irresCount += 1
            if user_email in irresBehavior:
                irresBehavior[user_email].append(date)
            else:
                irresBehavior[user_email] = [date]
            sorted(irresBehavior[user_email])

Lastly, the program will return irresponsible behavior and append it into a new text file, called "irresponsible_report.txt."

### Tracking system glitches

The third function is essentially a reversed version of the second function (irresponsible behavior). The program will use the same list generated for the second function and work through two more conditional statements. Again, these statements will look at how many times each employee logs on and off of any of the systems. Similar to the second function, this part of the program will also have an if statement stating that if the number of log offs are greater than log ins, it will be flagged as a system glitch. Whenever this is statement is true, it will equal to one system glitch. And the program will return the total amount of system glitches per employee.

### Tracking domain counts

The fourth function will be mainly composed of two lists and an if statement. The program will use the same list of employees from the second and third function. It will also use another list with all of the unique domains. The if statement will allow the user to see which employees belong to each unique domain. Lastly, the program will return how many employees belong to each domian and a list of the unique names.

### Tracking the employees who work the most

The fifth and final function of this program will analyze who of the 50 employees have worked the most throughout the month of May. The conditional statements will look at the dates and times that each employee logs in and out and how often they log in to the workstation server during the month. An if statement will be used to determine if an employee is logged into the workstation server for more than five hours, then that should be marked as working a full shift. Then, another if statement will be used to determine how many times each employee has logged in each day over the course of the entire month. There will also need to be elif statements to make sure that none of the log in/out attempts have been flagged as suspicious, irresponsible, or system glitches. By adding the elif statements, the program will return much more accurate and useful data. And lastly, the program returns the results of both if statements. 

### Updates:

One concept of this project that we had trouble with was
