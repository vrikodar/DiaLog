# DiaLog

DiaLog     
                            **D**etect **i**nspect **a**ct 

# Installation of DiaLog on Linux systems

            $ git clone https://github.com/SxNade/DiaLog
            $ cd DiaLog
            $ chmod +x setup
            $ ./setup

# DiaLog Config File

**DiaLog depends on dia.conf file to determine the service-type and log-file path to analyse**

                  # Format of conf File is                  
                  
                  service:path-of-log-file
                  
**So For example we are checking apache2 log file in /var/log/apache2/access.log our config file contents would look like this**

                    web:/var/log/apache2/access.log

**config file has the above entery by Default**

*Note:a user may add more than one enteries ....also note that currently only log analysis of standard apache2 access.log file is supported but soon features for analysing DNS log files and other services will be added*
