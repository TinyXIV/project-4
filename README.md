# UOCIS322 - Project 4 #
Joshua Muzi
CS 322
jmuzi04@gmail.com

## Overview

Reimplementation of RUSA ACP controle time calculator with Flask and AJAX.


### ACP controle times

This project consists of a web application that is based on RUSA's online calculator. The algorithm for calculating controle times is described here [https://rusa.org/pages/acp-brevet-control-times-calculator](https://rusa.org/pages/acp-brevet-control-times-calculator). Additional background information is given here [https://rusa.org/pages/rulesForRiders](https://rusa.org/pages/rulesForRiders). The description is ambiguous, but the examples help. Part of finishing this project is clarifying anything that is not clear about the requirements, and documenting it clearly. 

We are essentially replacing the calculator here [https://rusa.org/octime_acp.html](https://rusa.org/octime_acp.html). Which can be used to check any answers or data.

# Understand the application

The files calc.html found in the templates folder and flask_brevets.py work together using Flask and Ajax to send data being activiely typed in the calculator. 
Flask_brevets.py then access and gathers the data needed using request.args.get in "/_calc_times". 
The calc times function will then call two acp_times.py functions those being open_time and close_time which will calculate the times per control point given the RUSA control times calc https://rusa.org/pages/acp-brevet-control-times-calculator

# How to run the application

To get started you will need to be in your computer or laptop terminal and bring yourself to the project-4 brevets directory.
This can be done using 
cd project-4
cd brevets

To start running the application you will have to build it first using Docker and the following command. This will run Dockerfile which will install locally all required resources to run your application.
This can be done by repeating the following in your brevets directory terminal:

jmuzi@DESKTOP-GDPKR20:~$ docker build -t myimage .

Then to start the webpage and calculator you will need to run the following command after.

jmuzi@DESKTOP-GDPKR20:~$ docker run -p 5001:5000 myimage


Now that the webpage is working you are given some options to choose from to customize your race.

You will be able to determine the total distance of the race in segements of 200, 300, 400, 600, 1000

You then get the oppertunity to decide the date and time for the race.

Once this is finished you can begin to fill in check points that are equal to or below your total distance, going from smallest to biggest distance, starting at 0.




I also included 5 test cases using nose and assert which can be found in my test_acp_times.py file.

These can be tested by heading to the brevets directory and typing 

nosetests 
or I also found this works
nosetests3

All of which have passed, thankfully. 









## Grading Rubric

* If your code works as expected: 100 points. This includes:

	* Completing the frontend in `calc.html`.
	
	* Completing the Flask app accordingly (`flask_brevets.py`).
	
	* Implementing the logic in `acp_times.py`.
	
	* Updating `README` with a clear specification.
	
	* Writing at least **five** correct tests using nose (put them in `tests`, follow Project 3 if necessary) and all pass.

* If the algorithm is incorrect, 25 points will be docked off.

* If the webpage does not work as expected (JQuery or Flask failing to correctly fill in the information, etc.), 25 points will be docked off.

* If the test cases are missing/not functional/do not all pass, 5 points will be docked off per each (25 points total).

* If `README` is not clear, missing or not edited, or `Dockerfile` is not updated, up to 15 points will be docked off.

* If none of the functionalities work, 10 points will be given assuming `credentials.ini` is submitted with the correct repo URL, and `Dockerfile` builds and runs without any errors. 

## Authors

Michal Young, Ram Durairajan. Updated by Ali Hassani.
