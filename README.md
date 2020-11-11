# Project 3: Employee Log Report
## Group Members: Amanda Hernández, Alexandra Glick

## Overview

This is our third project for INST126 at the University of Maryland. For this project, we are pretending to be a part of a
professional working environment. Within most work environments, most software and digital activities are recorded using log files and that's where we come in. 
First, it's important to understand that the files analyzed contain information spanning a month. There are also 50 different employees. So, we first assesed the problem statement and came up with a plan of action that detailed how we would work through the problem. 

The goal of this program is to issue four reports that provide insights in four areas: suspicious activity, irresponsible behavior, system glitches, and domian countes. We will also provide an additional report that looks at which employee works the most. Ultimately, these reports are supposed to be used by higher officials to make decisions. 

## How it works

The code is composed of a total of five functions and one main dictionary data structure that will return all necessary information for each function. A function will be created for each report. There will a function to track suspicious activities, irresponsible behavior, and so on. By doing this, our code will be much more organized and cohesive. 

When a user runs the program, it will first import and read the log file that contains all of the information needed to create the reports. 

### Tracking suspicious activities

The first function has two conditional statements. The first checks if an employee logged into any of the system servers (mailserver.local, myworkstation.local, or webserver.local) more than five times in a single day. The second checks if any employees logged in between 12:00 a.m. to 5:00 a.m. Those who log in more than five times or log in between 12-5 a.m. will be marked as suspicious. The program will return the total number of suspicious activities. 

### Tracking irresponsible behavior 

The second function will contain a list of all 50 employees and have two conditional statements. The first conditional statement will count the number of times each employee has logged into any of the systems and the second statement will count the number of times each employee has logged off. An if statement stating if the number of logins are greater than the number of log offs will be implemented. Whenever that statement is true, it will be marked as an irresponsible activity and it will equal to one irresponsible activity. The program then returns the total amount of irresponsible activities per employee. 

### Tracking system glitches

The third function is essentially a reversed version of the second function (irresponsible behavior). The program will use the same list generated for the second function and work through two more conditional statements. Again, these statements will look at how many times each employee logs on and off of any of the systems. Similar to the second function, this part of the program will also have an if statement stating that if the number of log offs are greater than log ins, it will be flagged as a system glitch. Whenever this is statement is true, it will equal to one system glitch. And the program will return the total amount of system glitches per employee.

### Tracking domain counts

The fourth function will be mainly composed of two lists and an if statement. The program will use the same list of employees from the second and third function. It will also use another list with all of the unique domains. The if statement will allow the user to see which employees belong to each unique domain. Lastly, the program will return how many employees belong to each domian and a list of the unique names.

### Tracking the employees who work the most

The fifth and final function of this program will analyze who of the 50 employees have worked the most throughout the month of May. The conditional statements will look at the dates and times that each employee logs in and out and how often they log in to the workstation server during the month. An if statement will be used to determine if an employee is logged into the workstation server for more than five hours, then that should be marked as working a full shift. Then, another if statement will be used to determine how many times each employee has logged in each day over the course of the entire month. There will also need to be elif statements to make sure that none of the log in/out attempts have been flagged as suspicious, irresponsible, or system glitches. By adding the elif statements, the program will return much more accurate and useful data. And lastly, the program returns the results of both if statements. 

### Updates
