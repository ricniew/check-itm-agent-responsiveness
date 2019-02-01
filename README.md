# Check ITM Agent responsiveness
Check if agent is up and running and responds to requests

Author: Richard Niewolik

Contact: niewolik@de.ibm.com

Revision: 0.1

#

[1 General](#1-general)

[2 Installation](#2-installation-script-only)

[2.1 Supported Operating System](#supported-operating-system)

[2.2 Preparation](#preparation)

[3 Usage](#3-usage)

[3.1 Syntax](#syntax)

[3.2 Sample executions for Configuration](#sample-executions)

[4 Troubleshooting](#4-troubleshooting)

[5 Appendixes](#5-appendixes)


#

1 General
=========

Sometime in IBM Tivoli Monitoring (ITM), agents that are reported to be online are not doing it's job. Hence situations are not running and you will not get alerts for the thresholds you are monitoring. This can be costly. It is almost not possible to find those agents by using the ITM provided mechanism. Such agents occasionally time out when real time data is requested and the status will be set to off line, but not always. They will be called as "not-responsive" agents further in this document.

Mostly you are alerted by your application administrators or customers that they did not get any event for their business application, even an ITM sitution was set up to monitor a specific condition. Usualy you check agent's health by a Tivoli Enterprise Portal real time data request, for example a disk usage report. If the agent goes off line after such request, you start it again. If it remains on line your next action would be to check the logs and restart agent for quick problem resolution. After agent restart you will most likely execute several tests to verify agent's behavior. All of the tests will mostly be successfull. However, it remains an insecure feeling because you do not know when and where the problem reoccurs. 

This solution will help you to monitor not-responsive agents and avoid manual work to find those agents before hand.

2 Installation script only
==========================

Download the latest release of the script [here](https://github.com/ricniew/ibm-itcam-silent-config/releases) and unzip to a temporary directory on the host were your ITCAM Agent\+Datacollector and WebSPhere server are running. It
contains following files:

-   one ..

-   two ...

Supported Operating System
--------------------------

Procedure was tested on Windows and Linux Redhat + Suse but should run on other
UNIX and Linux Operating systems. 

Preparation
-----------

The created response files contains configuration options which are
valid for the most popular set up with a DC monitoring a WebSphere
instance. For the authentication client SOAP properties are used.
**Please check below for possible changes you may need to perform.**
Always check the created response file if it meets your required set up.
<br/>  
 
1.  **Text:**

       -   text *itme1*

       -   text *itme2*

       -   Integration of the DC with the *Tivoli Performance Monitoring*

       -   Integration of the DC with the *ITCAM Diagnostics Tool*

       -   Integration of the data collector with *ITCAM Agent for WebSphere version 6* (for Version 7.3 only)

     If you would like to use any of that options the procedure must be
     modified and the function *CreateConfigRespFile* needs to be adjusted
     with the required options to be used (modify *False* to *True*)

       > \# bla \
       > bla
       > 

<br/>   

2.  **Text:**

       -  text *itme1*

3 Usage
=======

Syntax
------

> xxxxxxxxxxxxxxxxx{ -h ITM home } \[ -p \]\

          
Sample executions
-----------------

bla

4 Troubleshooting
=================


5 Appendixes
============



bla
