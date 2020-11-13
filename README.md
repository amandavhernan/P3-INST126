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

To generate our second report, we created a dictionary called "irresBehavior" and set a variable, named "irresCount" to 0 to begin with. Next, we utilized iterations in order to create expressions for the variables "loginCount" and "logoutCount." To implement this code correctly, we created two conditional statements; the first conditional statement counts the number of times each employee has logged into any of the systems and the second conditional statement  counts the number of times each employee has logged off. An if statement stating if the number of logins are greater than the number of log offs will be implemented. If that statement is true, it will be marked as an irresponsible activity and "irresCount" will increase by one.

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

To generate our third report, we created a dictionary called "glitch" and set a variable named "glitchCount" to 0 to begin with. Next, we utilized the same exact iterations from the irresponsible behavior implementation in order to create expressions for the variables "loginCount" and "logoutCount." This report is essentially a reversed version of the implementation for the irresponsible behavior report. So, for the implementation of system glitches, we simply swapped the positions of "loginCount" and "logoutCount" in the first conditional statement from the irresponsible behavior code. After running this program, system glitches will be returned and appended to a new text file, called "glitch_report.txt."

### Tracking domain counts

To generate our last report, we created one more dictionary, called "domainsDict," and used the "keys" function to access the list of emails from the "logsDict" dictionary. This implementation consisted of a for loop and a conditional statement. Overall, this implementation allowed every unique domain to be printed out into a new text file along with the number of users registered within each domain.

The following code represents our conditional statements:

      for user_email in user_emailList:
      emailParts = user_email.split('@')
      domain = emailParts[1]
      if domain in domainsDict:
            domainsDict[domain] += 1
      else:
            domainsDict[domain] = 1
            
Lastly, the program will return domain counts and append it into a new text file, called "domain_report.txt."

### Tracking the employees who work the most (not implemented)

For the fifth and final function of this program, we wanted to create a function that would have analyzed who out of the 50 employees have worked the most throughout the month of May. The conditional statements would have looked at the dates and times that each employee logged in and out and how often they logged in to the workstation server during the month. An if statement would have been used to determine if an employee was logged into the workstation server for more than five hours, then that should be marked as working a full shift. Then, another if statement would have been used to determine how many times each employee has logged in each day over the course of the entire month. There would have also needed to be elif statements to make sure that none of the log in/out attempts have been flagged as suspicious, irresponsible, or system glitches. By adding the elif statements, the program would have returned much more accurate and useful data. And lastly, the program would have returned the results of both if statements.

Unfortunately, we spent an incredible amount of time trying to implement this code, but we couldn't get it to function.

### Errors:

1. When creating our global dictionary, we first used the ".read" function to read the file. However, when we did this, we kept getting an error stating that all of the list indexes for the lines of the text file were "out of range." At first, we honestly didn't know why this was happening at all and tried several different things to fix this, but then we finally realized that all we had to do was simply change it to ".readlines."
