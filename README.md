# Check ITM Agent responsiveness
Check if agent is up and running and responds to requests

Author: Richard Niewolik

Contact: niewolik@de.ibm.com

Revision: 0.1

#

[1 General](#1-general)

[2 How it works](#2-how-it-works)

[3 Supported Operating System](#3-supported-operating-system)

[4 Prerequisites](#4-prerequisites)

[2 Installation and Usage ](#2-installation-and-usage)

[2.1 Supported Operating System](#supported-operating-system)

#

1 General
=========

Sometime in IBM Tivoli Monitoring (ITM), agents that are reported to be online are not doing it's job. Hence situations are not running and you will not get alerts for the thresholds you are monitoring. This can be costly. It is almost not possible to find those agents by using the ITM provided mechanism. Such agents occasionally time out when real time data is requested and the status will be set to off line, but not always. They will be called as "not-responsive" agents further in this document.

Mostly you are alerted by your application administrators or customers that they did not get any event for their business application, even an ITM sitution was set up to monitor a specific condition. Usualy you check agent's health by a Tivoli Enterprise Portal real time data request, for example a disk usage report. If the agent goes off line after such request, you start it again. If it remains on line your next action would be to check the logs and restart agent for quick problem resolution. After agent restart you will probably execute several tests to verify agent's behavior. All of the tests will mostly be successfull and issue appears to be solved. However, it remains an insecure feeling because you do not know when and where the problem reoccurs. 

This solution will help you to monitor not-responsive agents and avoid manual work to find those agents before hand. It can be used in two different ways *Standalone script* or *Agent Builder Custom Agent*.

2 How it works
==============

The heart of this tool is a simple Perl script. Mainly doing the following:

   - Using SOAP to connect to the IBM HUB Server
   - Creating an agent status list before real time data request 
   - Retrieve real-time data from the agents 
   - Creating an agent status list again
   - Check for which agents no data have been returned and reporting those agents to STDOUT and/or into file.


3 Supported Operating System
============================

Procedure was tested on Windows and Linux Redhat + Suse but should run on other
UNIX and Linux Operating systems. 


4 Prerequisites
===============

Following PERL packages are used and needs to be available

       >use LWP::UserAgent;
       >use XML::Simple;
       >use Getopt::Long;
       >use Data::Dumper;
       >use File::Basename;
       >use Time::Local;
       >use Sys::Hostname;

2 Installation and Usage
========================

Please refer to the Wiki https://github.com/ricniew/check-itm-agent-responsiveness/wiki



