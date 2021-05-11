# DiaLog

DiaLog     
                            **D**etect **i**nspect **a**ct 

# Installation of DiaLog on Linux systems

            $ git clone https://github.com/SxNade/DiaLog
            $ cd DiaLog
            $ chmod +x setup
            $ ./setup
            
# A VERY VERY IMPORTANT NOTE

**BY DEFAULT DiaLog will Display and Log Requests of Resource if they were made more than 5 times**

**so if a Log file contains requests made to a resource less than 5 times it will be Ingnored**

**Don't Change to 0!**

*This behaviour can be changed by editing the weblogger.py File as Shown in the infographic Below*

*The change needs to be made in the mal_req_analysis function*

![Capture](https://github.com/SxNade/DiaLog/blob/main/extras/change.gif)

# Running DiaLog

            # Syntax
                
                $ chmod +x dia
                $ ./dia <white_ip>
  
  *The white_ip is the IP address of your server which you want DiaLog to Ignore*
  
  * If the IP address of my Server is **192.168.43.179** then my DiaLog command would Look Like this *
  
                    $ ./dia 192.168.43.179

![Capture](https://github.com/SxNade/DiaLog/blob/main/extras/dia.gif)

**After Every Run Remove results2.txt File or Make a Backup of it and then remove** 

# DiaLog Config File

**DiaLog depends on dia.conf file to determine the service-type and log-file path to analyse**

                  # Format of conf File is                  
                  
                  service:path-of-log-file
                  
**So For example we are checking apache2 log file in /var/log/apache2/access.log our config file contents would look like this**

                    web:/var/log/apache2/access.log

**config file has the above entery by Default**

*Note:a user may add more than one enteries ....also note that currently only log analysis of standard apache2 access.log file is supported but soon features for analysing DNS log files and other services will be added*

# New Feature

**A new Feature has be added to DiaLog that Allows the user to Gather some Passive Info about the Malicious IP's Discovered from the Log Ananlysis**

![Capture]()

*The Passive Info Gathered About The HOSTS Include*

            #1) Basic Info such as RDNS and Location Info
            #2) Open Ports on The Target Host
            #3) Potentical CVE's That the Target Host may be Vulnerable to

**This Has also been Hosted on a Different Project named JitterBug Follow the Link Below**

**-->** https://github.com/SxNade/JitterBug

# What Does DiaLog Do ?

**Nothing Like machine Learning is Going on here**

*Following with the current status and configurations loaded*
            
            #1) DiaLog searches For Frequencies of all the IP addresses accessing your server ie In the very First step it checks How many Times an IP address is appearing in the Log File to Determine the number of Total Requests made by that IP
            
            #2) In the second step DiaLog Breaks Down the Requests and Displays what resource on the web-server was Tried to access by the same IP more than 5 times ....you can also change this Frequency in weblogger.py file with a simple sed command below
            
            #3) All the Results found are Displayed on the Terminal window ...tommorow a small piece of code to add the Output to a text File will be added

# Giving custom path of conf File on the Go

**If you want to give custom path of conf File on the go then the Syntax is as Follows**

          $ ./dia <custom_conf_file_path> 192.168.43.179


# More Info

**For More Specific Info about DiaLog Please Read the man.txt File in extras**

https://raw.githubusercontent.com/SxNade/DiaLog/main/extras/man.txt

*This man.txt File will be updated soon*

