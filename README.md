Small-scale SOC Home Lab made using an Ubuntu Server virtual machine with Splunk SIEM and a Windows 11 virtual machine acting as the target of the attacks, sending its security logs to the SIEM.

The Windows 11 virtual machine generates logs, then these logs get ingested by the Ubuntu Server SIEM and get displayed on its web interface. The attacks used on the target machine were simulated manually and/or by using basic scripts to automate them.

In this project I simulated a basic full attack lifecycle; brute force attacks, clearing the machine's security logs, unauthorized creation of new users on the machine, trying to escalate the user's privileges, and unauthorized service creation. Detected them using logs, and provided full-scale reports and security measures for all of them.
